# [Day18] 免費授權圖庫 ＆ 圖示庫

## 免費授權圖庫

- [skitterphoto](https://skitterphoto.com/)：以 CCO(Creative Commons Zero)授權釋出。除了可直接使用、也可以修改，甚至是用在商業用途上。並且不用特別標註來源與作者名稱。數量不多，多為拍攝者自行上傳，所以圖感也比較自然點

![Imgur](https://i.imgur.com/7AAIGJr.png)

- [Pixabay](https://pixabay.com/)：也是 CCO 授權。這裡不只有圖片，還有影片跟音樂的素材可以使用。據說內容已經超過 180 萬個素材，算是相當豐富。因為網站規模大，所以也有多國語系可以切換喔

![Imgur](https://i.imgur.com/s7qVieP.png)

- [pexels](https://www.pexels.com/zh-tw/)：跟 Pixabay 一樣，規模跟數量都非常完整。還有個特別的地方是能以[API 方式](https://www.pexels.com/api/)取得圖片，只要加入會員，並且提出 API key 的申請就可以使用

![Imgur](https://i.imgur.com/Hr4uMhy.png)

## 圖示庫

- [Font Awesome](https://fontawesome.com/?from=io)

![Imgur](https://i.imgur.com/ipEZqOr.png)

Font Awesome 是一套發展滿成熟的圖示庫。近期預計會推出版本 6，將會提供更多圖示與功能。Font Awesome 有分兩種使用方案：免費版可以使用 1600 多種圖示，而付費版則有快 8000 個圖示可以使用。

剛開始要用的話，可以先看一下官方提供的[文件](https://fontawesome.com/how-to-use/on-the-web/referencing-icons/basic-use)。使用上完全不用 CSS 和 Javascript 的加工，只要在 HTML 中使用`<i>`或`<span>`標籤設定 class 就好

```html
<i class="fas fa-camera"></i>
<!-- this icon's 1) style prefix == fas and 2) icon name == camera -->

<i class="fas fa-camera"></i>
<!-- using an <i> element to reference the icon -->

<span class="fas fa-camera"></span>
<!-- using a <span> element to reference the icon -->
```

而 icon 的樣式目前有分成五種，每一種都有他的 prefix 設定。

![Imgur](https://i.imgur.com/3A7hkxk.png)

- [System UIcons](https://systemuicons.com/)

如果專案中比較少地方會用到圖示，而且使用到的圖示比較單純常見，那 System UIcons 也是個不錯的選擇。如果只是想要其中幾個圖示，有三種方式可以使用：

1. 點選圖示區塊，就能複製 SVG 的程式
2. 複製 CDN 的連結
3. 下載為 SVG 檔案

如果你會用到蠻多的話，也可以一次下載全部的圖示到專案中喔。

![Imgur](https://i.imgur.com/v23IAvc.png)

- [Tabler icons](https://github.com/tabler/tabler-icons)

Tabler icons 有超過 850 種以上的圖示，並提供兩種方式可以下載：

1. 從[Github](https://github.com/tabler/tabler-icons)找想要的檔案下載
2. NPM `npm install --save tabler-icons`

想看 Tabler icons 有哪些圖示可以看以下

![png](https://raw.githubusercontent.com/tabler/tabler-icons/master/.github/icons.png)

使用的方式在 Github 寫的蠻清楚的，主要有以下方式

1. 在 HTML `<img>` 標籤來源引入

   ```html
   <img src="path/to/icon.svg" alt="icon title" />
   ```

2. 在 HTML `<svg>` 標籤以 class 指定

   ```html
   <svg
     xmlns="http://www.w3.org/2000/svg"
     class="icon icon-tabler icon-tabler-disabled"
     width="24"
     height="24"
     viewBox="0 0 24 24"
     stroke-width="1.25"
     stroke="currentColor"
     fill="none"
     stroke-linecap="round"
     stroke-linejoin="round"
   ></svg>
   ```

這個套件還有一個方便的地方是可以覆蓋直接以 class 覆蓋預設設定

```css
.icon-tabler {
  color: red;
  width: 32px;
  height: 32px;
  stroke-width: 1.25;
}
```

- [CSS.gg](https://css.gg/)

![Imgur](https://i.imgur.com/L4EFWyn.png)

第一個吸引我的地方是名稱很可愛ＸＤ(喂)

這個圖示庫目前有 700 多種圖示，並且有多種方式可以引入，像是 NPM 安裝、以 API call 匯入 或 svg 下載等。

以 NPM 安裝來說，指令為 `npm install --save css.gg`。

CSS.gg 厲害的地方是支援度很高，不管是 Styled Component, SVG Sprite, HTML 標籤等等都可以使用。以下是他的資源檔路徑與類型列表。

![Imgur](https://i.imgur.com/vaFuoMg.png)

## 小結

今天整理的東西對視覺的呈現上還蠻有幫助的，像圖示庫的部分，工程師就可以跟視覺設計師討論要以哪個圖示庫來導入專案中，彼此的溝通上也會有更多的共同語言，也能幫助視覺設計師減少重做 icon 的勞力，將心力可以放在更重要的排版與操作流程的設計。

## 參考資源

- [Skitterphoto 免費相片圖庫以 CC0 授權釋出可自由下載使用](https://free.com.tw/skitterphoto/?fbclid=IwAR1ez5b0aRbdp9xdB9oLL8eLSwo05kS6nDkLmBKXgY7oM3Zng_Fm2rissR0)
- [10+ Awesome CSS & Javascript Icon Libraries 2020](https://bashooka.com/coding/css-javascript-icon-libraries-2020/)
