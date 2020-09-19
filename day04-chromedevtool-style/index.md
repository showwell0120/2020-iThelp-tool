# [Day04] 瀏覽器開發工具 - 樣式篇

今天要來介紹跟樣式有關的檢視與調校，一樣我們以開發情境來一一說明如何操作。

## 切換偽類的效果

開發者工具支援以下四種偽類(Pseudo-classes)的樣式檢視與編輯
 
- `:active`：當目標元素正被點擊或選取時
- `:focus`：目標元素成為頁面的焦點時
- `:hover`：滑鼠移動到目標元素時
- `:visited`：目標元素點擊過後的狀態

1. 選取目標元素後，點擊 樣式側欄的 **:hov**
2. 這時會展開所有偽類的選項，勾選之後就能顯示對應的樣式效果

![gif](https://i.imgur.com/WIUsEPT.gif)


## 使用調整間距和大小

除了在樣式區調整樣式設定，還能用 Box Model 直接對特定值進行設定。  

1. 選取目標元素後，樣式側欄移到最下面，會有一個矩形的示意圖。顯示上下左右的 **margin**、**border** 和 **padding** ，以及目標元素的 **width x height** 的數字
2. 雙擊數字，就可以輸入其他數字觀察變化

![gif](https://i.imgur.com/geI4Y3t.gif)

## 檢視未被使用到的樣式設定
   
當我們想幫檔案瘦身時，就會想要移除掉不用的部分。開發者工具可以幫開發人員檢查那些程式或樣式是沒有使用到的， 甚至還會計算檔案的涵蓋率，相當實用。   

1. 鍵盤按 **Ctrl + Shift + P 或 Cmd + Shift + P (Mac)** 就能開啟命令列選單
2. 接著輸入 `coverage`，會出現建議選項
3. 點選 `Start Instrumenting Coverage And Reload Page` 就會自動載入頁面，並且在下方長出 **Coverage**的tab，並顯示結果
4. 可以選擇篩選CSS 或是 JS 檔案。這裡選擇CSS
5. 雙擊檔案，就會在上方顯示檔案。紅色的部分表示有使用到；藍色則表示未使用到

![gif](https://i.imgur.com/ofLZB2g.gif)

## 小結

透過今天的整理，可以發現在樣式上不只是能做到一般的調整，還能針對程式進行優化，讚讚！

## 學習資源
- [小事之 CSS 偽類 與 偽元素](https://ithelp.ithome.com.tw/articles/10196924?sc=hot)
- [Get Started With Viewing And Changing CSS
  ](https://developers.google.com/web/tools/chrome-devtools/css)
