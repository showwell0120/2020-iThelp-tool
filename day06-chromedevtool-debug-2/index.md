# [Day06] 瀏覽器開發工具 - 除錯篇(下)

## 觀察執行結果

當每次程式暫停在斷點時，除了要觀察頁面上的變化，很多時候還需要監測運算後的變數。  
所以我們需要利用開發者工具現有的功能來方便做這些事情。

### Scope(作用域)

在左方或下方的側欄中，展開 **Scope**，其中有三種選項可以展開

- **Local** : 目前進入的函式的所有變數的數值顯示
- **Closure** : 根據層級的不同，分別顯示所有的閉包函式
- **Global** : 顯示全域變數與列出相關變數與方法。通常是指 `Window`

![Imgur](https://i.imgur.com/Hgj5zA3.png)

### watch(監看)

有時候我們想針對特定的變數，在除錯過程中可以持續觀察變化。因此我們可以使用這個功能來實現。

選取變數，點選右鍵，選擇 **Add selected text to watches**，就能將目標變數加入監看區。

![Imgur](https://i.imgur.com/eXoxWYY.png)

### Console drawer

想對當前作用域的變數進行其他運算時，可以在底下的 **Console drawer** 直接取得變數來做其他操作。

![gif](https://i.imgur.com/C8WLfZ5.gif)

## 修改後取消斷點再執行

當我們已經發現問題，通常想即時修改程式來驗證解決方法。但如果開發環境中沒有 hot reload 機制，就比較難做到這件事。

在開發者工具裡，我們只要雙擊程式區，就能進行編輯。完成後就能按 ctrl+s 儲存，並再次執行。

### 取消斷點設定

如果問題都解決的差不多，希望先停止所有斷點的執行，這時可以先啟用 **Deactivate all breakpoints**，讓程式可以正常運作。

![Imgur](https://i.imgur.com/YwWyQXj.png)

以上就是一般除錯過程中，經歷的一些步驟跟調校的技巧分享。

## Snippets

在開發者工具，我們最常使用的就是開啟 **Console**，輸入一段程式碼檢查輸出結果。不過如果有一段程式我們很常會重複執行，或者是程式部分比較複雜，每次要複製貼上也相當麻煩。

因此開發者工具有提供 **Snippets** 功能，將常用的程式片段儲存在瀏覽器中，並方便在裡面管理或執行現有的 snippets。

1. 在開發者工具的 **Sources** 的右方資源區，點選 Snippets Tab
2. 點選 **New Snippet**，新增檔案
3. 輸入檔案名稱
4. 輸入程式內容
5. 如果要執行，可以點選右下的播放鍵，或按 Ctrl+Enter，或對檔案按右鍵，選擇 Run
6. 如果要更改名稱、移除、另存新檔，對檔案按右鍵選擇對應選項

![gif](https://i.imgur.com/9VHc0A7.gif)

## 小結

呼呼 除錯篇就這樣先告一個段落啦!  
想當初在上手這部分的時候，也花了一段時間適應除錯的流程。
如果有什麼使用心得，歡迎底下留言交流喔。

## 參考資源

- [Run Snippets Of JavaScript On Any Page With Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)
