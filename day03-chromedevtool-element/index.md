# [Day03] 瀏覽器開發工具 - 元素篇

今天的主題是針對在元素(Element)面板上可以進行的動作，包括對頁面上的元素進行結構的變動，或著樣式上的檢視。廢話不多說，直接切入正題吧！

## 對當前選取到的元素進行操作

![Imgur](https://i.imgur.com/rumlGAh.png)

當元素呈現被選取的狀態，除了會反白以外，右方還會加上 `== $0` 的字樣。這表示可以直接在 console 下 **`$0`** 來代表這個元素，進行相關操作。

這樣一來就不用先以 `document.querySelector`等選取 的 API 來獲得元素，方便許多。

![Imgur](https://i.imgur.com/4F2TNyR.gif)

## 讓目標節點顯示在目前畫面上

對節點按右鍵 > 點選 **Sroll into view** 就能完成，十分簡單。

![Imgur](https://i.imgur.com/tp7idR8.gif)

## 將當前選取到的元素存到全域

對節點按右鍵 > 點選 **Store as global variable**，開發者工具就會馬上為它建立變數，並且以名稱 `tempN`來命名不同的元素，方便之後的操作。

![Imgur](https://i.imgur.com/ytmK7p2.gif)

## 查看元素的偽元素效果

對節點按右鍵 > 點選 **Force state** > 點選想要呈現的效果，瀏覽器就會強制套用樣式。不用辛苦地來回測試囉！
![Imgur](https://i.imgur.com/2nPWaXO.png)

## 小結

寫完這篇才知道，原來我對 Chrome 開發者工具真的只是略懂皮毛 😂  
連最基本的調校元素，也能做到很多事情！  
感謝 iT 鐵人賽讓我有機會學到更多東西 😆

## 學習資源

- [Get Started With Viewing And Changing The DOM](https://developers.google.com/web/tools/chrome-devtools/dom)
