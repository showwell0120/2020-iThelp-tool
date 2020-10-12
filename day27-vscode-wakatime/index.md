# [Day27] VSCode Plugin - WakaTime

- [官網連結](https://wakatime.com/dashboard)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=WakaTime.vscode-wakatime)
- 推薦程度：⭐⭐⭐⭐⭐

有在寫工作日誌或週誌，或是想了解自己到底花了多少開發時間的人，非常大力推薦使用 WakaTime。

WakaTime 主要功能是從各面向來追蹤編輯器的操作時間，包括專案名稱、程式語言、作業系統等等，並且在官網登入後，就可以看到各種統計圖表。想要主動接收統計訊息的話，也可以設定 e-mail 通知。

另外如果成為付費會員的話，可以自訂查詢時間來產生圖表，以及使用 Teams 這種團隊協作的功能等。不過個人使用的話，其實免費的就很好用囉！

加入會員之後，我們可以先看看 [WakaTime 支援哪些編輯器](https://wakatime.com/plugins)。目前共支援了 49 種編輯器，連設計師專用的 Sketch，甚至是 word 都可以使用。

點進編輯器的圖示後，會顯示安裝步驟。

![Imgur](https://i.imgur.com/5I7tfy1.png)

登入官網後，進到設定頁面，可以看到 Account 的資訊中有一欄 **API Key**。這就是允許編輯器中追蹤操作紀錄的憑證。點選複製，待會會用上。

![Imgur](https://i.imgur.com/3WpSICX.png)

在 VSCode 安裝完 plugin 後，可以按**F1**開啟指令列，輸入`wakatime`，選擇 `WakaTime:Api Key`。把剛剛複製的 Secret API Key 貼上並按 Enter。

![Imgur](https://i.imgur.com/U2ujVFC.png)

![Imgur](https://i.imgur.com/qYkeIH1.png)

如果想要定期收到統計結果的話，可以在設定頁面的 **Email notifications** 設定頻率、發送時間和專案篩選。另外其他相關的信件通知也可以在這裡設定。

![Imgur](https://i.imgur.com/HKodOi0.png)

收到的信件會根據以下的分類進行時間統計 -

1. Projects: 專案列表
2. Languages: 程式語言列表
3. Editors: 編輯器列表
4. Operating Systems: 作業系統列表
5. Categories: 操作行為列表
6. Machines: 使用的機器列表

![Imgur](https://i.imgur.com/2C1t8M8.png)

如果想看比較圖形化的結果，可以到官網上的 Dashboard 看。

![Imgur](https://i.imgur.com/XZC5Dfh.png)

如果想看特定專案的統計圖表，也可以到專案列表中查詢。

![Imgur](https://i.imgur.com/BFg4CQF.png)
