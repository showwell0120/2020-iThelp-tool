# [Day14] 色彩好用工具

身為前端工程師，除了要實作功能互動以外，還有很重要的就是視覺上的呈現。

在前期的開發階段，為了盡量讓產品的原型看起來有感覺一點，通常前端工程師自己就要先懂一些配色，讓頁面看起來不至於太醜；到了後期 UI Designer 的加入，我們要做的則是可以把顏色的設定能精準到位。

因此，今天就來認識五個各種情境下好用的色彩工具吧！

## ColorPick Eyedropper

- 類型：chrome 擴充功能
- 簡介：針對網頁的所有元素，可以放大檢視，並任意點擊取得錨點，就能獲得錨點處的色碼。
- 推薦理由：Designer 給初步的設計稿時，可以直接同步設計稿的顏色設定，或是想從圖片中汲取顏色時非常方便。
- [商店連結](https://chrome.google.com/webstore/detail/colorpick-eyedropper/ohcpnigalekghcmgcdcenkpelffpdolg)
  ![img](https://lh3.googleusercontent.com/T2K8gPFaBVfgxw8kl1SoIVJQcC_LsdfikpvyMbiKJ0IlUyKFJ7W-m2huUVCmlqB6fYeOE_pPMQ=w640-h400-e365-rj-sc0x00ffffff)

## colorize

- 類型：VSCode 外掛
- 簡介：在 CSS 中，在任何形式的顏色設定的色碼上，都可以背景色顯示在編輯頁面中。
- 推薦理由：一目了然看顏色是否有設定對
- [市集連結](https://marketplace.visualstudio.com/items?itemName=kamikillerto.vscode-colorize)
  ![gif](https://raw.githubusercontent.com/kamikillerto/vscode-colorize/master/assets/demo.gif)

## Google

- 類型：網站
- 簡介：直接以顏色設定的 CSS 作為關鍵字搜尋，在 Google 搜尋結果上就會出現各種形式的設定還有調色盤
- 推薦理由：快速查看顏色以及各種形式的設定
- [範例連結](https://www.google.com/search?q=%236b6b6b&oq=%236b6b6b&aqs=chrome..69i57j0l7.14624j0j4&sourceid=chrome&ie=UTF-8)

![Imgur](https://i.imgur.com/kFyEnUc.png)

## Canva Color Palette Generator

- 類型：網站
- 簡介：可以透過圖片取得各種的主題色配置系列，可以自己上傳圖片取得，也可以直接從裡面非常多張的樣板配置取得。個人覺得是個非常厲害的應用。
- 推薦理由：可以直接以形象圖來取得各種顏色的配置，不用再挑色挑半天。
- [網站連結](https://www.canva.com/colors/color-palette-generator/)

![Imgur](https://i.imgur.com/Z0YZfkG.png)

## EggGradients

- 類型：網站
- 簡介：用很可愛的蛋形呈現 200 多種以上的漸層色配置，並且跟會根據每年設計趨勢來做調整。
- 推薦理由：可以根據色系來選各種美美漸層色，而且可一鍵複製 CSS 設定。
- [網站連結](https://www.eggradients.com/)

![Imgur](https://i.imgur.com/wUc2QMN.png)

```css
.xxxx {
  /*複製的設定*/
  background-color: #a40606;
  background-image: linear-gradient(315deg, #a40606 0%, #d98324 74%);
}
```
