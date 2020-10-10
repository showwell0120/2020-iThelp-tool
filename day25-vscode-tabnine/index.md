# [Day25] VSCode Plugin - TabNine

從今天開始到第 29 天，我將會整理 VSCode 的一些 Plugin 介紹。今天要看的是，想靠機器學習一統 Snippet 世界的 TabNine。

![gif](https://i.imgur.com/wRqiOxM.gif)

- [官網連結](https://www.tabnine.com/)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=TabNine.tabnine-vscode)
- 使用方式：直接安裝即可
- 推薦程度：⭐⭐⭐⭐

> TabNine uses deep learning to help you write code faster.

在 VSCode 中，我們以往都會根據開發的語言來安裝對應的 snippet plugin，來幫助撰寫時，可以出現建議選項，讓我們可以少打一點字。

像是寫前端的 Javascript 會有[JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets); 寫 Laravel 的可以安裝[Laravel Snippets](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel5-snippets)等等。

不過這些常用的 snippets，都是以程式語言的角度來設計，所以機制上很單純，看你的輸入會適配到哪些關鍵字，就顯示對應的語法選項。

而 TabNine 卻是站在開發者的角度，以輸入的程式碼作為機器學習的素材。不僅可以像一般 snippets 出現語法的建議選項，如果在開發過程中有重複的 pattern 出現時，TabNine 也會預測接下來開發者要輸入的內容，並顯示在選項上。

例如輸入了 - `const a = [1,2,]`，TabNine 就會預測開發者是想輸入連續的數字列表。所以就會出現以下選項 -

![Imgur](https://i.imgur.com/SYnmF8w.png)

支援度的部分，其實還蠻廣泛的。以編輯器來說，除了 VSCode 以外，還 Sublime Text、Vim、Atom 等官方套件可以使用。語言的部分他號稱是所有的程式語言都有支援。

就我使用的心得，的確在預測 pattern 輸入的部分還蠻厲害的，減少許多相似模式的程式撰寫。不過有個缺點是，如果有在 VSCode 中有裝其他 snippets，在大部分情況就會被 TabNine 取代選項，這部分大家可以自行斟酌囉。

最後想了解更多 TabNine 的訓練機制，可以前往第二個參考資源喔！

## 參考資源

- [小克的 Visual Studio Code 必裝擴充套件（Extensions）私藏推薦](https://blog.goodjack.tw/2018/03/visual-studio-code-extensions.html#javascript--vue)
- [工程師殺手級工具！一秒自動補齊後續程式碼，還支援 23 種程式語言](https://buzzorange.com/techorange/2019/08/02/nice-coding-tool/)
