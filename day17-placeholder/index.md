# [Day17] Placeholder & Fake Data

進行前端開發時，如果只是在進行原型階段，或是視覺和 API 還沒 ready 時，我們最常做的就是塞假資料，讓畫面看起來至少會有東西，而且也比較好做排版。

不過如果沒有仰賴工具的輔助，我們通常要自己找素材、下載，然後再匯入到專案中。這樣的工作其實蠻耗時，而且不見得可以找到適合的素材。

所以今天我從相似用途的工具中，挑了一些覺得不錯的來看看，希望對你也會有點幫助喔。

## 線上工具

### 圖片

### [Dynamic Dummy Image Generator](https://dummyimage.com/)

![gif](https://i.imgur.com/NGbBPt7.gif)

最基本也是彈性的圖片產生工具。可以設定大小、背景色、文字色還有文字內容。調整完後會即時呈現在畫面上，並且產出連結，像這樣 -  
`https://dummyimage.com/300x200/f6f6f6/6a6a6a.png&text=Hello`

如果只是想單純放圖片示意大小跟用途的話，這個工具還蠻適合的囉。

#### [PlaceIMG](http://placeimg.com/)

![Imgur](https://i.imgur.com/crdNgr4.png)

可以按照分類產生隨機的圖片。長寬的大小限制為 1000px，然後可以有兩種濾鏡模式以及五種分類可以選擇。選完之後就可以複製網址使用。另外如果不指定分類的話，把網址後面的分類名稱改成`any`就可以囉。

### 文章

#### [Loripsum](https://loripsum.net/)

![Imgur](https://i.imgur.com/sgAS3dl.png)

大多的假文產生工具提供的功能就是複製文字。不過 Loripsum 還可以設定段落數、長度甚至還能加入 HTML 的元素樣式，讓文章看起來更像是編輯器產出的文章。

#### [亂數假文產生器](http://www.richyli.com/tool/loremipsum/)

![Imgur](https://i.imgur.com/SRjjaE3.png)

這個工具的最大特色是： 1. 繁中 2. 快速選定字數。推薦想呈現中文字在頁面上的人喔。

## NPM

### [Facker.js](https://github.com/marak/Faker.js/)

- [npm](https://www.npmjs.com/package/faker)

![png](https://raw.githubusercontent.com/Marak/faker.js/master/logo.png)

Facker.js 算是蠻有名的 mock 資料的函式庫。而且支援度也很高，在前端或 Node.js 都可以引入使用。像這樣 -

- 前端：下載檔案，使用`<script>`標籤匯入

```javascript
<script src="faker.js" type="text/javascript"></script>;
const randomName = faker.name.findName();
```

- 後端：安裝 NPM 模組

```javascript
npm install --save faker
const faker = require('faker');
```

- 以 API 方式取得

````
http://faker.hook.io/?property=name.findName&locale=en
```

Facker.js提供的假資料欄位非常多。如果要建立有使用者資訊的應用，這裡該有的欄位幾乎都有提供。

他還有一個主要特色是可以設定語言，連繁中也有喔！星星數有25多Ｋ果然有他厲害的地方。

他還有個[DEMO頁面](https://cdn.rawgit.com/Marak/faker.js/master/examples/browser/index.html)，也可以先去玩玩看熟悉一下喔。

## 參考資源

- [12 個你應該知道的中英文假字、文章產生器（Lorem Ipsum）](https://free.com.tw/lorem-ipsum-generator/)
````
