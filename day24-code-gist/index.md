# [Day24] 實現技術的查詢

今天介紹的偏向查詢類的實用工具。當想開始上手某個技術或語法時，我們可能會先想了解相關的使用情況。這時候就可以使用一些方式來幫助我們先做一點市場研究。

## Can I Use

- 類型：網站
- [網站連結](https://caniuse.com/)

應該不少人在做跨瀏覽器支援時，或多或少都有用過這個工具。不管是 JS 或是 CSS，推陳出新的速度很快，但是各家瀏覽器的版本支援通常是沒辦法完美同步。所以很常時候當要使用實驗性功能，或是相當新的語法時，我們必須要知道各個瀏覽器的支援情況。

比如最近推出的新的圖片格式`WebP`，如果想在專案中導入，就要先看[支援度](https://caniuse.com/webp)如何。

- 在結果頁面左上，會有這個特性的基本介紹，還有報告的顯示設定。
  ![Imgur](https://i.imgur.com/H3sfpGj.png)

- 預設的顯示是按照各瀏覽器的不同，和其版本的推進排列顯示。如果綠色表示正常使用; 橄欖色表示部分情況可以使用; 紅色則表示目前還不支援。
  ![Imgur](https://i.imgur.com/ZmnUdxs.png)

- 另外可以選擇 Usage Relative 的選項改變顯示結果。版本區塊的大小會依使用者的分佈成比例顯示，可以從使用者的角度來看這個功能對於哪些多數使用者的支援情況。
  ![Imgur](https://i.imgur.com/eehZ1Ie.png)

## Wappalyzer

- 類型：網站 / 瀏覽器擴充功能
- [網站連結](https://www.wappalyzer.com/)
- [擴充功能下載連結](https://www.wappalyzer.com/download/)

當工程師總是會有滿滿的好奇心，看到有興趣的網站或應用就會想知道前端是不是用了什麼框架？主機環境架設在哪裡？內容管理的平台是什麼？甚至是流量分析、SEO 等等。

Wappalyzer 在首頁有提供網址輸入查詢的功能，不過需要登入會員使用，並且每月有 50 次的限制。

1. 點 Look up a website  
   ![Imgur](https://i.imgur.com/r47gwbA.png)

2. 輸入網址  
   ![Imgur](https://i.imgur.com/E6KGTqu.png)

3. 顯示分析結果。以 Facebook 為例，可以看到前端框架使用 React、RxJS，後端使用 PHP，並使用 HTTP/2 等。  
   ![Imgur](https://i.imgur.com/XXGWwEi.png)

Wappalyzer 還有提供免費的瀏覽器擴充功能安裝，在 Chrome、Firefox 和 Edge 上可以使用。操作上其實更直覺，直接在想查看的網址能點選擴充功能就好。

我們來偷看一下 iT 邦的技術組成。像是前端是使用 Vue，伺服器使用到 Nginx 管理，並且使用 jQuery、Hightlight.js 等函式庫。
![Imgur](https://i.imgur.com/7GAE3Y9.png)

## 參考資源

- [Wappalyzer —  查看網站所使用的環境、技術、主機與分析工具，一覽無遺！](https://meethub.bnext.com.tw/wappalyzer%E2%80%8A-%E2%80%8A%E6%9F%A5%E7%9C%8B%E7%B6%B2%E7%AB%99%E6%89%80%E4%BD%BF%E7%94%A8%E7%9A%84%E7%92%B0%E5%A2%83%E3%80%81%E6%8A%80%E8%A1%93%E3%80%81%E4%B8%BB%E6%A9%9F%E8%88%87%E5%88%86/)
- [6 个前端开发必备工具，提高你的生产力](https://blog.csdn.net/shiyanlou_chenshi/article/details/104699206)
