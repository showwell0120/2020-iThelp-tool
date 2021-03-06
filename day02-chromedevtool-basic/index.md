# [Day02] 瀏覽器開發工具 - 基本篇

## 前言

瀏覽器的開發工具對於大多數的 Web 前端工程師來說，就像是陽光空氣水一樣，從踏入開發的一開始就不能沒有它。從最基本的檢查 DOM、調整樣式到效能檢查、網路偵測等。對於工程師們來說，每天跟它見幾次面已經算是日常了。

而目前 Chrome 仍然是瀏覽器屆中的霸主 (不過換了 chromium 為核心後的 Edge，市佔率已經超過 firefox，接下來是否有機會抬頭哩?我們繼續看下去 🧐)

加上 Google 對於開發者工具的發展也頗有用心，一直都有持續拓展新功能，方便 Web 開發人員進行更全面的檢測與調試。因此在接下來的這幾天，會依照我的專案經驗，重點式的介紹 Chrome DevTools 的主要應用情境與操作的小技巧。

![dev tool](https://developers.google.com/web/tools/chrome-devtools/javascript/imgs/open-settings.png?hl=zh-tw)

## 如何開啟開發者工具?

根據情境與目標，可以選擇適合的方式開啟

1. 針對當前頁面：  
   在 Windows 按**F12**即可。  
   Mac 則囉嗦一點同時按 **Cmd + Opt + I**
2. 針對固定的 DOM 節點：  
   需要觀察 DOM 的結構和樣式，在頁面的該目標按 **右鍵>檢查**
3. 針對不固定的 DOM 節點：  
   DOM 節點會因其他瀏覽器事件的觸發而消失。比如開發選單元件，需求是當元件失去焦點，像是任意點擊頁面，就會馬上銷毀。

   這時如果嘗試第 2 種方式，當開啟開發者工具的介面時，元件對應的 DOM 就會被移除，無法對元件進行除錯或檢查。這種情況可以這樣做

   - 以第一種方式開啟開發者工具
   - 這時預設選取的節點是`body`，按**方向鍵的&#8595;或&#8593;**，可移動選取目前顯示在面板上的節點。  
     接著按**方向鍵的&#8594;**，可以展開目前選取的下一層子節點。重複方向鍵的操作，直到展開目標節點。

     ![dev](https://i.imgur.com/puPlJ44.png)

## 小結

蝦咪?! YURI 今天就只說怎麼開啟開發者工具嗎?! 才第二天就偷懶啊 🙄

沒錯！因為時間有限，而且我相信大部分的基本操作，很多人用著用著就上手了。所以在內容上只會放我覺得比較 tricky 一點，或是我覺得頗重要的部分。

所以以今天來說，可以著墨的就這些了。如果是初學者的話，建議可以到 Google 的官方教學，或自己開出來隨便按按就會上手啦 😉

## 參考資源

- [全球瀏覽器最新戰況](http://technews.tw/2020/05/08/the-best-web-browsers-for-android-in-2020/)
- [Chrome DevTools - 鍵盤快捷鍵參考](https://developers.google.com/web/tools/chrome-devtools/shortcuts?hl=zh-tw)
