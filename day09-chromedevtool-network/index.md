# [Day09] 瀏覽器開發工具 - 網路篇

當我們使用 **LightHouse** 和 **Performance** 的面板找出前端程式可優化的地方，接下來就是看我們開發的應用，在進行網路請求的時候，速度上和資料的正確性是否都能符合預期。

接下來就切到 **Network** 面板一起練習看看吧!

## 選項與設定

上方的前兩排，主要是顯示請求紀錄的調整選項與設定。  
而在第一排的在右方，有一個齒輪，點擊後可展開細部的選項，這些選項主要可以增加一些資訊量，幫助開發者解析。

![Imgur](https://i.imgur.com/MVKNLVN.png)

以我來說，比較常用的有

1. 模擬連線的環境。例如想模擬手機的連線，可以選 **Slow 3G**
2. 顯示所有請求的 Timeline，跟 Performance 的 Timeline 一樣可以範圍選取
3. 顯示每個 frame 的頁面截圖
4. 篩選請求紀錄表格的資源類型，例如只看非同步的請求，則選 **XHR**
5. 清除請求紀錄的所有內容
6. 可根據輸入文字篩選符合的路徑

## 錄製請求

跟 **Performance** 一樣，我們可以使用錄製功能來紀錄特定期間的請求紀錄。通常會有兩個時機點與啟用方式 : 

- **Ctrl+R** : 頁面自動重新載入，並開啟錄製狀態
- **Ctrl+E** : 啟動錄製狀態

結束後再按左上方的紅點 **(Stop Recording network log)**，或按**Ctrl+E**結束錄製。

![gif](https://i.imgur.com/HP6befE.gif)

## 調整表格欄位

在請求紀錄表格中，預設的顯示欄位並不會全部顯示。如果想要調整欄位的話，可以在表格標題處按右鍵，切換欄位的勾選狀態即可。

![Imgur](https://i.imgur.com/5jPaM3h.png)

## 分析請求內容

![Imgur](https://i.imgur.com/XInRD1d.png)

當點選某一則請求時，右方會出現請求的詳細資訊，包括

- Headers : 可以查看由前端發送出去與接收到的封包header資訊
- Preview : 回傳資料的最佳預覽格式，方便開發者查看。
- Response : 回傳資料的原始格式。
- Initiator : 可以看發送請求的call stack
- Timing : 以長條圖顯示各種狀態時的時間長度。

![Imgur](https://i.imgur.com/YW2DNdG.png)

## 小結

今天的內容相信有些經驗的開發人員都非常熟悉。如果有其他覺得實用技巧或操作流程，歡迎留言分享喔。

## 參考資源

- [Chrome Devtools 開發者工具功能介紹(network 篇)](https://www.astralweb.com.tw/chrome-devtools-developer-tools-network/)
- [Inspect Network Activity In Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/network)
