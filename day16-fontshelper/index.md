# [Day16] Google Webfonts Helper

- [應用連結](https://google-webfonts-helper.herokuapp.com/fonts)
- [source code](https://github.com/majodev/google-webfonts-helper)

今天介紹的是 YURI 個人常用的字型工具 - Google Webfonts Helper。

當專案需要設定外部的字型檔時，我們可能會以直接引入的方式向遠端抓字型下來，像這樣

```css
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+TC&display=swap");
```

不過如果網路環境問題，造成下載字型檔過慢，有可能會在等待期間，讓使用者看到設定前的樣式。因此為了提升速度與穩定性，可以選擇把字型檔下載下來，並放在專案目錄裡。

Google Webfonts Helper 不只可以簡單做到這件事情，也能夠透過介面的方式產出相關的 CSS 設定，還有提供瀏覽器最佳化的字型設定。接下來就來看看怎麼操作吧！

1. 選擇字型。目前提供 1005 種的字型可以選擇。  
   ![Imgur](https://i.imgur.com/smpn0Y1.png)

2. 選擇`charsets`。以 **Noto Sans TC**(Google 開源的中文字型)為例，有 chinese-traditional 跟 latin 可選擇  
   ![Imgur](https://i.imgur.com/dVFZbgx.png)

3. 選擇預設文字大小與粗細  
   ![Imgur](https://i.imgur.com/cS1REGc.png)

4. 依專案需求選擇支援程度，如果需要跨裝置跟跨瀏覽器支援的話，選擇 Best Support。在程式碼底下可以填入到時候儲存字型檔的目錄路徑，程式碼的部分會即時變動。調整好後就能複製程式碼到專案上  
   ![Imgur](https://i.imgur.com/somuzUe.png)

5. 下載壓縮檔到專案目錄，解壓縮  
   ![Imgur](https://i.imgur.com/i2VaGPQ.png)

希望今天整理的可以幫助到你囉！
