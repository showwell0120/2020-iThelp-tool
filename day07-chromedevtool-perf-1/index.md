# [Day07] 瀏覽器開發工具 - 效能篇(上)

完成除錯後，接著就要幫我們開發的頁面進行效能上的檢測和優化。在現在各種裝置的普及，前端應用也愈多樣複雜，使用者對於速度也就愈要求。

為了提升使用者的體驗，開發者工具提供了蠻全面的工具，幫助開發人員找出程式中的效能瓶頸在哪裡。

在這個篇章，我們會依序使用到兩種主功能面板，來完成效能優化的目的

- **Lighthouse**: 燈塔，顧名思義是「協助避免觸礁」。透過檢測程式的執行，方便找到問題，並提供解決建議，協助達到最佳實踐
- **Performance**: 性能面板。環境模擬、錄製執行期間的行為、分析結果等

今天我們就從可愛貓貓 Tony 的教學範例開始吧！

![jpg](https://developers.google.com/web/tools/chrome-devtools/speed/imgs/tony.jpg)
(原來google的貓貓都那麼厲害)

1. 在網址上輸入 `chrome://version` 確認版本是在68之後
2. 前往想測試的網站
3. 在 Lighthouse 中，勾選 **Performance** 以及想執行的裝置
4. 網站載入結束後，呈現檢測的完整報告。我們試著來讀讀看吧！


  - 在報告上方，最明顯的就是分數的部分。透過數值和顏色的顯示，可以快速掌握效能的好壞。   
    展開右上方的更多，可匯出報告為特定格式，支援度還蠻高的。
    
    ![Imgur](https://i.imgur.com/Aj1yE0S.png)   

       
  - **Metrics(指標)**
  
    Lighthouse 以使用者的角度，針對效能部分建立了6個主要指標。透過這部分的結果，可以找出主要問題是在哪裡。

    1. **First Contentful Paint(FCP)**: 第一個任意可見元素渲染在頁面的時間
    2. **Speed Index**: 載入頁面時，視覺上變化的速度
    3. **Largest Contentful Paint**: 最大面積的元素渲染在頁面的時間
    4. **Time to Interactive (TTI)**:  使用者可與瀏覽器互動，並可給予回應的時間
    5. **Total Blocking Time(TBT)**:測量主程序被超過 50ms的任務 block 的時間
    6. **Cumulative Layout Shift(CLS)**: 累計版面配置轉移。可見元素因意外造成位移的分數總和

    View Trace 的按鈕會導向 Performance 面板，我們會在明天詳細介紹。

    ![Imgur](https://i.imgur.com/kEFpWyL.png)

    
  - **opportunities(機會)**
  
    這裡會列出修改建議，並顯示大約可節省的時間是多少。例如列出容易造成頁面blocking的JS/CSS檔，並計算出優化過後的檔案可到多大，節省多少時間。

    ![Imgur](https://i.imgur.com/ap3kH7D.png)

    
  - **Diagnostics(診斷)** 

    針對效能部分提出更多細部的問題檢視與修改建議方式。例如避免 `document.write()`、避免DOM的大小過大等。

    ![Imgur](https://i.imgur.com/rAqGolw.png)

  - **Runtime Settings**

    列出這次執行檢測的環境設定，方便進行比較。
  
    ![Imgur](https://i.imgur.com/1gNLt9u.png)


## 小結

今天介紹的 LightHouse 其實不只應用在效能的改進上，其他像是建構PWA或改善SEO等，都必須靠它來完成。而 LightHouse 也不只在開發者工具上才有
。有機會的話，後續會再整理相關資源。

## 參考資源
- [審查面版](https://ithelp.ithome.com.tw/articles/10194220)
- [Lighthouse Metrics：以使用者為出發點來探討效能的指標](https://cythilya.github.io/2020/09/07/lighthouse-metrics/)
- [超前部屬很重要！2021年Google排名的重要指標之一 – CLS指標](https://www.ls-design.com.tw/news_detail_SEO_Cumulative_Layout_Shift.html)
- [Chrome 推出 Lighthouse 前端稽核功能 – 為了更好的 SEO 與使用者體驗](https://www.astralweb.com.tw/google-lighthouse-for-front-end-audits-to-imporve-better-seo-and-user-experience/)
- [Optimize Website Speed With Chrome DevTools](https://developers.google.com/web/tools/chrome-devtools/speed/get-started#audit)
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)