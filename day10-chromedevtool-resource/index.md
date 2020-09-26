# [Day10] 瀏覽器開發工具 - 資源篇

今天我們來看看跟網站資源比較相關的兩個面板 - **Applications** 跟 **Security**。

為了要展示面板功能與設定，我們以大家熟悉的 [星巴克 PWA 版](https://app.starbucks.com/) 來認識看看這兩個面板分別有哪些用途吧!

## Applications

這個面板主要是集中管理與顯示網站相關的資源與相關的服務資訊。右邊呈現詳細的項目內容，左邊為選單，並依項目類型分群顯示，像是 **Storage**、**Cache** 等。

![Imgur](https://i.imgur.com/WFT2ePs.png)

以在 **Application** 的 **Manifest** 為例。當我們要開發 PWA 時，會需要有份設定檔來告訴瀏覽器說這是 PWA 的應用。在這裡就可以清楚看到設定檔的資訊，以及是否有疏漏或錯誤的地方。

![Imgur](https://i.imgur.com/tR3OuM8.png)

另外在 **Application** 的 **Service Workers**，我們可看在這個網站中有註冊哪些 Service Worker（SW），以及 SW 的相關資訊。

![Imgur](https://i.imgur.com/xgqjmAc.png)

再來 **Application** 的 **Clear Storage** 算是開發或除錯的時候蠻常使用到的功能。

除了可以直覺地看到目前資源的使用容量，還可以一次列出所有的網站資源或啟用的服務，並可以選擇性的移除部分或全部。算是十分方便的功能。

![Imgur](https://i.imgur.com/FKTAbaL.png)

在這個面板，我們也可以查詢特定資源的詳細資料。例如打開 **Storage** 的 **Cookies**，可以看到某個 origin 底下的所有 cookies。點擊某個 cookie 列表，在底下就能清楚看到 cookie 的值。

## Security

安全性的部分主要是看這個網站本身，以及透過請求存取資料的外部 origin，是否都為安全連線（https）。現在的瀏覽器的發展愈來愈注重資料傳輸的安全性與加密，所以也算可以方便開發人員可以快速總覽每個 origin 的憑證與相關資訊。

![Imgur](https://i.imgur.com/VqhLetU.png)

如果有 http 連線的 origin，瀏覽器會告訴開發者說這是不安全的。

![Imgur](https://i.imgur.com/cX6FiTG.png)

## 小結

今天講的各種資源檢視，其實不只需要前端工程師熟悉，後端服務或架設站台等開發人員也能透過這些工具可以直接驗證網站存取到的資源是否正確，並且是否提供足夠的安全性。希望對大家在開發上都有所幫助囉！

## 參考資源

- [【译】一文洞察 Chrome DevTools 近半年新增了哪些功能](https://www.zoo.team/article/chrome-devtools)
- [Understand Security Issues With Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/security)
