# [Day05] 瀏覽器開發工具 - 除錯篇(上)

接下來整理的部分是我覺得這個 part 最重要的內容之一。

人不是神，只要有寫程式的一天，就會面臨臭蟲的到來 (除非你是想先甘後苦，總之先交給 QA 的那種類型，但最好不要啦 XD)。

所以在這個題目上，我會分成兩天進行。今天會按照除錯的流程，介紹每一步驟該有的思維和工具的使用。重點流程分別是

1. 發現問題 ，並列下產生問題的步驟
2. 依問題類型下**斷點(Breakpoints)**
3. 視情況決定暫停執行的方式
4. 觀察執行結果
5. 修改後取消斷點再執行

一樣這裡不會介紹太多的基本知識，像是個工作區的介紹等，有興趣的可以在前往官方資源查看喔。

## 發現問題 ，並列下產生問題的步驟

第一步就是要看到問題。不過可以的話，還需要盡量列出問題發生的必要條件或者步驟。當然這要看問題的大小或複雜度。

我認為只要符合以下這些情況的 bug，就可以先替這個問題列出相關說明

- 需要進行 3 個步驟以上的動作才能重現。
  e.g. input 文字輸入 > 點擊確認鍵 > 點擊選單項目 > ...
- 產生問題的行為不只有一種方式。例如以滑鼠或以方向鍵選擇選單項目都無法運作

## 依問題類型下斷點(Breakpoints)

接下來就要看問題點在哪，是屬於哪一種類型的問題，以及對問題的掌握度來下中斷點。

### 主程式

通常直接下在主程式的特定行數，會是因為對問題的掌握度較高，比較清楚出錯的地方在哪。
不過有些情況是雖然無法得知確定的行數，不過能大概推測出幾個關鍵的地方，這時候也是可以下多個中斷點去檢查。

![Imgur](https://i.imgur.com/nT7PwTn.png)

主程式的中斷點列表在右方或下方的 Breakpoints 的區域，可以切換勾選狀態，或點右鍵進行移除或忽略等。

### DOM

如果對問題掌握度沒那麼高，而且是出在 DOM 節點變化上的問題，這時候就可以從 Element 中的目標節點下中斷點。

1. 在目標節點點擊右鍵，選擇 **Beak on**
2. 有三種中斷條件可選擇
   - **subtree modifications** 子節點更新
   - **attribute modifications** 屬性更新
   - **node removal** 該節點被移除

![Imgur](https://i.imgur.com/555Xx1I.png)

### Event Listeners

如果對問題掌握度沒那麼高，而且是出在觸發瀏覽器監聽事件後的問題，可以開啟目標事件來下斷點。

1. 展開右方或下方的 **Event Listener Breakpoints**
2. 勾選想開啟的瀏覽器監聽事件即可

![Imgur](https://i.imgur.com/dmQzENq.png)

### XHR/fetch

有些時候我們知道問題是出在遠端資料更新到前端時，這時我們可以篩選出特定的 API，並且當對這些 API 發出請求時來下斷點。

1. 展開 **XHR/fetch Breakpoints**
2. 點擊右方的+
3. 輸入特定的字串為篩選條件
4. 確認此條件有被勾選即可

![Imgur](https://i.imgur.com/TU4YAwl.png)

### Pause on exceptions

當頁面因意外錯誤而卡住，卻無法即時確認出問題的行數在哪，就可以開啟這個選項，就能把斷點下在發生意外錯誤的地方。

![Imgur](https://i.imgur.com/N6mPoFu.png)

## 視情況決定暫停執行的方式

![Imgur](https://i.imgur.com/2dKCJk4.png)

### 1. Step over next function call

程式只暫停在下個函式呼叫的地方，其他地方會正常執行。

以官方範例來說，在 A 暫停時，點選該按鍵或快捷鍵**F10**，A 函式的實作(B and C)會正常執行，接著在 D 就會再暫停。

```javascript
function updateHeader() {
  var day = new Date().getDay();
  var name = getName(); // A
  updateName(name); // D
}

function getName() {
  var name = app.first + " " + app.last; // B
  return name; // C
}
```

### 2. Step into next function call

進入函式時，實作的每一行都會暫停。

以官方範例來說，在 A 暫停時，點選該按鍵或快捷鍵**F11**，在 B 就會停下來。

```javascript
function updateHeader() {
  var day = new Date().getDay();
  var name = getName(); // A
  updateName(name);
}

function getName() {
  var name = app.first + " " + app.last; // B
  return name;
}
```

### 3. Step out of current function

跳出目前執行的函式。

以官方範例來說，在 A 暫停時，點選該按鍵或快捷鍵**Shift+F11**，B 會正常執行，接著在 C 暫停。

```javascript
function updateHeader() {
  var day = new Date().getDay();
  var name = getName();
  updateName(name); // C
}

function getName() {
  var name = app.first + " " + app.last; // A
  return name; // B
}
```

### 4. Step

這部分要開放給大大們解惑了。因為自己鮮少用到，加上目前官方文件好像還沒有更新說明，不是很清楚這個的用途。目前只覺得跟 step into 還蠻類似的，知道的大大們再請你們在底下留言，開示小妹。

## 小結

啊啊啊今天時間來不及，就先到這邊啦 ！明天會繼續把剩下的整理完
不過今天的內容對在座每位前端真真真的很重要啊！
所以如果看完後覺得有什麼可以補充，或是哪裡有錯誤的地方，趕快在下方讓 YURI 知道喔，謝謝大家～

## 參考資源

- [Get Started with Debugging JavaScript in Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/javascript)
- [[學習筆記] Chrome Dev Tools 開發者工具實用功能整理](https://pjchender.blogspot.com/2017/06/chrome-dev-tools.html)
