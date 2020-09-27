# [Day12] 瀏覽器開發工具 - 燈塔篇(Lighthouse)

在[Day7](https://ithelp.ithome.com.tw/articles/10242054)的介紹中，我們初步認識了 Lighthouse ，在效能的檢測上可以發現問題，並且給予修改上的建議。

![Imgur](https://i.imgur.com/VNiPNdw.png)

但 Lighthouse 其實還有其他面向的檢測功能，來幫助我們的應用可以更貼近使用者，以提升體驗。接著就來看看這些項目吧！

## Progressive Web App (PWA)

PWA(漸進式網路應用程式)最主要的目的，就是讓網頁的瀏覽方式，也能有類似在行動裝置上可安裝的、即時回應的使用體驗。

除了新增必須的 `Manifest.json` 和其他靜態資源以外，主應用的可響應性(RWD)、渲染速度、安全性等等也需要達到一定標準。

因此在 Lighthouse 裡，針對 PWA 的檢測會提出三大面向的問題建議

- **Fast and reliable(快速且可靠的)**：當在行動網路時回應夠不夠快？離線狀態時是否有回 200 等
- **Installable(可安裝的)**：是否使用 HTTPS？是否有 `Manifest.json` 進行相關設定？是否有註冊 Service Worker？
- **PWA Optimized(PWA 優化)**：是否有 `Manifest.json` 進行細部設定？是否有提供完整的靜態資源檔(例如 icon)？

![Imgur](https://i.imgur.com/eHxSWJY.png)

## Best Practices

針對頁面內容，對程式上主要有四個面向的問題建議，

- **Trust and Safety(信任度與安全性)**：存取的連結是否安全？JS 是否有安全上的漏洞等
- **User Experience(使用者體驗)**：圖片大小是否適當等
- **Browser Compatibility(瀏覽器兼容性)**：是否有設定正確的 `doctype`等
- **General(一般)**：在 console 是否有出現錯誤等

![Imgur](https://i.imgur.com/dz9mrNP.png)

## Accessibility

無障礙設計是個不管在視覺設計或前端開發上，都需要多花一些心思去實踐。

Lighthouse 一樣提供不同面向的問題，並且提供開發者修改建議

- **Contrast**：改善內容的易讀性。例如背景與文字顏色的對比等
- **Navigation**：使用鍵盤來導覽網站的容易程度
- **Names and labels**：透過語意性的設定來使用網站
- **Internationalization and localization**：語言的在地化。例如有無設定 `lang` attribute
- **Tables and lists**：是否有為表格或列表等內容提供輔助性科技協助使用。例如使用`screen reader`

![Imgur](https://i.imgur.com/qWd26D1.png)

## SEO

- **Mobile Friendly** ： 行動裝置友善，使用者不需再調整頁面，例如有無 `<meta name="viewport">`的 tag
- **Content Best Practices**：是否有用語意性的 tag 以及設定完整的 attribute 等，讓爬蟲方便抓取

![Imgur](https://i.imgur.com/VU6bXV3.png)

## Publisher Ads (beta)

- **Ad Speed**：廣告速度，載入時間是否太久行程效能瓶頸
- **Tag Best Practices**：廣告版面的 UI 設定是否恰當等

![Imgur](https://i.imgur.com/j8nGA1W.png)

## 小結

經過今天的整理，如果有想要提升網站質量的話，那不妨先跑一下 Lighthouse，在優化上也會有效率很多喔！

## 參考資源

- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
