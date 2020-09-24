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

另外，因為 Timeline 會錄製所有行為，包括非網站本身的請求等(像是擴充功能的初始化)。建議錄製前先關閉所有擴充功能。或者是直接以無痕視窗進行錄製喔

![gif](https://i.imgur.com/ZVEeuVk.gif)

### 分析 Timeline

#### 總覽

可以看到整個載入到渲染完成，需要 5.71 秒的時間，其中我們可以看到花最久的時間是 **Scripting**(JS 執行的時間)，大約就花了 4.2 秒；其次是 **Rendering**(渲染時間)。

![Imgur](https://i.imgur.com/mNkbass.png)

#### 列表

在 **Bottom Up** 、 **Call Tree** 跟 **Event Log**可以看到所有資源運作的詳細記錄。我們可以點擊某個執行的函式，點擊右方的檔案連結，就可以到 **Sources** 查看這個函式，並且可以在行數旁邊看到執行時間等。

![Imgur](https://i.imgur.com/SMioGZM.png)

![Imgur](https://i.imgur.com/oSoTNxo.png)

#### 選擇範圍

可以選取特定時間，讓底下的細部資料只呈現選取時間內的紀錄。

1. 點擊一下 Timeline，這時會出現選取框
2. 可左右拉曳到想要的長度
3. 滑鼠移到選取範圍內，當鼠標變成手掌形，表示可以拖曳選取框改變位置

![gif](https://i.imgur.com/l9jKFf2.gif)

#### 圖層

![Imgur](https://i.imgur.com/uQW15V7.png)

Timeline 總共有四個圖層，由上到下依序為

- **FPS**: 瀏覽器的順暢度，也是效能的重要指標。綠色區塊表示比較流暢，紅色區塊表示畫面比較卡頓。這時候可以展開底下的 **Frames**，移到特定 frame 上，可顯示這時的 frame 的 FPS 數值是多少。

![Imgur](https://i.imgur.com/rciqC2Q.png)

- **CPU**: 以波浪圖顯示各資源運作的消耗比率。顏色的參考可以看上面的總覽。像是占最多比率的黃色，是指**Scripting**(JS 執行)；其次的紫色是 **Rendering**(渲染)

- **NET**: 可以顯示請求階段的紀錄，這時候可以展開底下的 **Network**， 藉由位置跟長度可以了解請求的順序和花了多久時間完成。

![Imgur](https://i.imgur.com/4SZ6ayM.png)

- **HEAP**: JS 引擎中，Memory 儲存複雜的資料結構，例如物件、函數等的區域。這時候可以展開 **JS Heap**的曲線圖，可以更清楚了解這段時間，Memory 的存取狀況為何。

![Imgur](https://i.imgur.com/ObgUoSb.png)

## 小結

呼呼~ 雖然有小遲到一下，不過終於整理完了!  
透過效能的檢測，我們不只可以發現問題，也能了解瀏覽器的運作細節。  
對於想成為優秀的前端來說，這算是必備的技能之一喔!

## 參考資源

- [檢測效能的好幫手 Chrome Devtool Performance](https://medium.com/@Lieutenant1992/%E6%AA%A2%E6%B8%AC%E6%95%88%E8%83%BD%E7%9A%84%E5%A5%BD%E5%B9%AB%E6%89%8Bchrome-devtool-performance-2ae96e7c4f69)
- [Chrome DevTools — Timeline](https://segmentfault.com/a/1190000008608538)
- [Performance Analysis Reference](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)
- [了解瀏覽器的棧內存 (Stack) ＆ 堆內存 (Heap)](https://medium.com/@bigboys.me/%E6%99%AE%E9%80%9A%E9%A1%9E%E5%9E%8B%E5%92%8C%E5%B0%8D%E8%B1%A1%E7%9A%84%E5%8D%80%E5%88%A5-%E6%A3%A7%E5%85%A7%E5%AD%98-stack-%E5%A0%86%E5%85%A7%E5%AD%98-heap-44295724848c)
