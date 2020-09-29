# [Day13] 瀏覽器開發工具 - 自行開發篇

這個系列的最後，我想要整理一下如何開發擴充功能的起手式。

從前面的介紹可以大致了解各種主要情境下的操作，以及針對前端開發上可以使用的偵錯工具。

但是有些情況下還是無法用現有功能來滿足。例如我們開發了一個頻繁向伺服器請求資料的應用，並且需要對所有接收的封包做統計或視覺化了解運作是否正常。這時候我們就得自行開發符合需求的擴充功能，來加強開發者工具的應用範圍。

在一開始，我們可以透過官方的這張示意圖快速掌握開發者工具的擴充功能的基本架構。其中，有三大部分需要被實現 -

- **Background**：在 Background 中，可以使用完整的 extension API。所以 Background 通常會拿來做跟瀏覽器有關的事件處理中心，或是任務執行的地方。
- **Content scripts**：當擴充功能需要存取到頁面的 DOM 元素或是事件時，就可以在頁面上植入提供的 scripts 進行操作。
- **Devtools page**：實現擴充功能面版的視覺與功能，也是使用者主要操作的地方。

雖然是三個不同的程式進入點，不過在 extension API 中，都有提供訊息傳遞的接口。所以只要有實作接收或發送訊息的 listener，就能串連起整個程式架構。

![png](https://developer.chrome.com/static/images/devtools-extension.png)

接著我們對主要的檔案做基本的介紹。

## 設定檔 `manifest.json`

`manifest.json` 是設定擴充功能資訊的地方，包含設定版本、名稱，還有程式進入點等。

跟一般擴充功能比較不一樣的是，我們需要設定 `devtools_page`，也就是面板 UI 的實作頁面。

另外還有需要注意的有 -

- `permissions` 是告訴瀏覽器，這個擴充功能需要存取什麼權限。不過因為隱私權政策的升級，如果要上架到商店的話，還需要針對每個權限填寫正當理由，而且寫愈多，審核的時間就會愈長。所以盡量只寫必要權限就好。
- `content_security_policy` 是告訴瀏覽器擴充功能會存取這些來源的資源。如果沒有寫在這裡的來源，則會發生 CORS 的錯誤。

更多有關 `manifest.json` 可以參考[相關文件](https://developer.chrome.com/apps/manifest)。

```json
{
  "version": "0.0.1",
  "name": "擴充功能名稱",
  "manifest_version": 2,
  "devtools_page": "devtools.html",
  "background": {
    "scripts": ["background.js"]
  },
  "description": "擴充功能的描述",
  "web_accessible_resources": ["image/*"],
  "permissions": [
    "background",
    "contextMenus",
    "cookies",
    "notifications",
    "storage",
    "tabs",
    "webRequest",
    "webRequestBlocking",
    "<all_urls>"
  ],
  "content_security_policy": "default-src 'self'; script-src 'self' https://firebaseio.com 'unsafe-eval'; connect-src *; style-src * 'unsafe-inline' 'self' blob:; img-src * 'self' data:; font-src *;"
}
```

## Background

之前提到 Background 可以存取所有擴充功能有關的 API，也是主要的訊息溝通中心。我們來舉幾個情境看看。

### 初始擴充功能的事件 listener

使用 `chrome.runtiime.onInstalled` 來觸發安裝完成後的事件。

```javascript
chrome.runtime.onInstalled.addListener(function () {
  chrome.contextMenus.create({
    id: "cxtmenu-1",
    title: "Sample Context Menu",
    contexts: ["selection"],
  });
});
```

### 接收訊息的處理中心

使用 `chrome.runtiime.onMessage.addListener` 來處理接收到的訊息。

```javascript
chrome.runtime.onMessage.addListener(function (message, callback) {
  if (message.data == "change-color") {
    chrome.tabs.executeScript({
      code: 'document.body.style.backgroundColor="orange"',
    });
  }
});
```

## Content scripts

scripts 可以存取部分的擴充功能 API，像是 `chrome.storage`、`chrome.runtime.getURL`等。

例如我們要在頁面顯示某張圖片

```javascript
var imgURL = chrome.runtime.getURL("images/myimage.png");
document.getElementById("someImage").src = imgURL;
```

更多有關 `Content scripts` 可以參考[相關文件](https://developer.chrome.com/extensions/content_scripts)。

## DevTools

在 DevTools 中，最主要的是可以存取 `chrome.devtools.*` 和 `chrome.extensions.*` 相關的 API，來幫助開發面板的 UI。

在 `chrome.devtools.*`中，有三種 API 的集合 -

- **`devtools.inspectedWindow`**：在當前頁面下執行程式片段。例如檢查頁面中 jQuery 的版本。

  ```javascript
  chrome.devtools.inspectedWindow.eval("jQuery.fn.jquery", function (
    result,
    isException
  ) {
    if (isException) console.log("the page is not using jQuery");
    else console.log("The page is using jQuery v" + result);
  });
  ```

- **`devtools.network`**：取得在 **Network**面板看到的資訊。例如印出當前頁面發出請求的回應封包的 body 大小。

  ```javascript
  chrome.devtools.network.onRequestFinished.addListener(function (request) {
    console.log(request.response.bodySize);
  });
  ```

- **`devtools.panels`**：建立面板的 Layout。使用 `chrome.devtools.panels.create` 建立面板的基本部分 - 面板標籤與主要頁面引入。

  ```javascript
    chrome.devtools.panels.create(
        "PanelTabName",  // 標籤名稱
        "TabIcon",       // 標籤名稱旁的icon
        "Panel.html"     // 頁面路徑
        function(panel) { ... }  // 建立面板後的callback
    );
  ```

更多有關 `chrome.devtools` 可以參考[相關文件](https://developer.chrome.com/extensions/devtools)。

## 小結

今天終於替 chrome 開發者工具的系列做個結尾了，感覺好漫長呀！  
這裡有個小小心得就是，google 一直以來都有考量 Web 開發趨勢，不斷改良跟擴充開發者工具的功能。  
但在整理的過程中發現，就算是去年才寫的東西，可能以現在來看就又不太一樣。  
加上官方文件似乎更新的速度也趕不太上釋出的更新。  
所以希望目前為止整理的內容多少可以有些幫助喔！

## 參考資源

- [Extending DevTools](https://developer.chrome.com/extensions/devtools)
- [Chrome devtools extension 實作介紹](https://blog.techbridge.cc/2018/02/10/chrome-devtool-extension/)
