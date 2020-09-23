# [Day08] 瀏覽器開發工具 - 效能篇(下)

昨天主要介紹使用 Lighthouse 幫助我們從使用者的角度來發現問題與提供解決方式。今天則是要以程式的角度，以 **Performance** 面板裡的 **Timeline** 來幫助開發者做更細部的分析。

## 看懂 Timeline 前，先知道什麼是 `FPS`

> 影格率是用於測量顯示影格數的量度。測量單位為「每秒顯示影格數」（Frame per Second，FPS）或「赫茲」，一般來說 FPS 用於描述影片、電子繪圖或遊戲每秒播放多少影格。 (Wiki)

在瀏覽器中需要渲染動態的頁面，來完成頁面上的刷新與呈現。所以如果 FPS 愈高，表示頁面的過場和渲染就愈順暢；反之則會出現卡頓現象，造成使用者體驗的不佳。因此，FPS 成為了網站的性能指標之一。

而一般來說，瀏覽器的 FPS 大約在 60 左右。通常達到這個數值以上，表示頁面的順暢度是沒什麼太大問題的。

## 認識 Timeline

Timeline 是開發者工具中用來記錄一段時間內的發生的所有狀態、行為等。通常會有兩個時機點可以記錄

- 頁面初始載入，到所有內容渲染完成的期間
- 使用者與瀏覽器進行互動後，瀏覽器完成回應且渲染完成的期間

待會分析時會再詳細說明。

## 產生 Timeline

首先，我們得先產出 Timeline。步驟非常簡單，只要

1. 前往想要測試的網站
2. 開啟開發者工具 > 點選 **Performance**
3. 如果想要模擬硬體或連線環境，可以點擊右上方的齒輪，進行相關設定
4. 點選中間提示的第二行按鈕 **(Start profiling and reload page)** 後，瀏覽器會自動幫你重載頁面，並開始錄製。
5. 錄製結束後，即可出現相關圖表

![gif](https://i.imgur.com/ZVEeuVk.gif)

### 分析 Timeline

#### 總覽

可以看到整個載入到渲染完成，需要 5.71 秒的時間，其中我們可以看到花最久的時間是 `Scripting`(JS 執行的時間)，大約就花了 4.2 秒；其次是 `Rendering`(渲染時間)。

![Imgur](https://i.imgur.com/mNkbass.png)

#### Root activities

**Call Tree**

![Imgur](https://i.imgur.com/zH2vdqW.png)

####

## 小結

## 參考資源

- [檢測效能的好幫手 Chrome Devtool Performance](https://medium.com/@Lieutenant1992/%E6%AA%A2%E6%B8%AC%E6%95%88%E8%83%BD%E7%9A%84%E5%A5%BD%E5%B9%AB%E6%89%8Bchrome-devtool-performance-2ae96e7c4f69)
- [Chrome DevTools — Timeline](https://segmentfault.com/a/1190000008608538)
- [Performance Analysis Reference](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)
