# [Day11] 瀏覽器開發工具 - 擴充功能篇

雖然開發者工具中已經提供相當豐富的功能，也一直持續發展中。不過 Google 有開放提供可裝在開發者工具的擴充功能的 API，像是目前大多主流的前端框架的開發者，都有提供相關的擴充功能，方便使用框架開發應用的人可以進行除錯。

所以今天就來整理目前前端三巨頭 - React、Vue 跟 Angular 可以使用的擴充功能吧！

## React Developer Tools

- 最近更新：2020/7/18
- 官方提供：是
- 支援版本
  - **react-dom**：15.x 大部分支援 / 16.x 支援
  - **react-native**：0.62 後支援
- [商店連結](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi)
- [source code](https://github.com/facebook/react/tree/master/packages/react-devtools-extensions)

由官方 Facebook 提供給 React 開發者的除錯工具。因為 React 是以 vDOM 加上狀態管理觸發渲染的機制，所以在元素面版呈現的已經是更新過後的 DOM，並無法對元件的階層關係或狀態資料進行檢測或除錯。

為了方便開發者在瀏覽器中也能進行偵錯，官方的擴充功能主要有提供兩種功能

- **Components**：呈現元件的階層結構，查看 state、props 等資訊。
  ![img](https://lh3.googleusercontent.com/W5h-3Esx-a2cOq4TaQ2O5tz-zLMjTupUgJjiFF_wZfszDGHdlGpH0JeZoT29399vLdkRRQqBEeM=w640-h400-e365-rj-sc0x00ffffff)
- **Profiler**：與 Performance 面版相似。可錄製渲染過程，產生所有 call stack 的記錄圖表。在 React 官方文件中有詳細的[教學說明](https://zh-hant.reactjs.org/blog/2018/09/10/introducing-the-react-profiler.html)。
  ![gif](https://zh-hant.reactjs.org/99cb4321ded8eb0c21ae5fc673878563/see-all-commits-for-a-fiber.gif)

## Redux DevTools

- 最近更新：2018/12/19
- 官方提供：否
- [商店連結](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd?hl=zh-TW)
- [source code](https://github.com/zalmoxisus/redux-devtools-extension)

![img](https://lh3.googleusercontent.com/wfhSnnYEQc3TCXbRTpTloa-XZesgDt0xAogzGoLF1BUCU04aYhdwAjueJYTtDxfRiqjUfC539g=w640-h400-e365-rj-sc0x00ffffff)

如果有導入 redux 進行應用的狀態管理，那這個擴充功能算是必備工具啦。

只要有打開工具，從載入到使用者的每個動作所發送的 **Action** 跟 **State** 都會清楚的紀錄，並且我們最關心的狀態變化，也能透過 **Diff** 的功能觀察某個 action 後變動的值。

另外還有繪製 redux 的架構樹狀圖，方便開發者快速掌握了解應用的狀態管理，另外還有其他更深入的操作，可以參考官方提供的[教學文件](http://extension.remotedev.io/)喔。

## Vue.js devtools

- 最近更新：2019/11/25
- 官方提供：是
- [商店連結](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)
- [source code](https://github.com/vuejs/vue-devtools)

跟 React 一樣，可以瀏覽元件的階層關係、狀態值，甚至還可以對狀態進行修改，查看頁面的變化。

![im](https://raw.githubusercontent.com/vuejs/vue-devtools/dev/media/screenshot-shadow.png)

## Augury

- 最近更新：2020/2/2
- 官方提供：否
- [商店連結](https://chrome.google.com/webstore/detail/augury/elgalmkoelokbchhkhacckoklkejnhcd)
- [source code](https://github.com/rangle/augury)

跟以上提到的一樣的基本功能一樣，不過在圖表的呈現上還蠻完整的，像是 Injector Graph, Router Tree 等。

![img](https://lh3.googleusercontent.com/9rIh-NYM3_NV9pwXnpxFSE9pKnIeYAuc7zTapRuAha4iwowFNpZs9ozC5KD0C-FXZaXI81sd=w640-h400-e365-rj-sc0x00ffffff)
![img](https://lh3.googleusercontent.com/g61FFjibYFJKh82lCJXGwSjftjiJCWyc7fsALkEnPZRRF5TSf6ba643u_q7QXuMK7FdWxl1b9T8=w640-h400-e365-rj-sc0x00ffffff)

## 參考資源

- [Featured DevTools Extensions](https://developer.chrome.com/devtools/docs/extensions-gallery)
