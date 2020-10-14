# [Day29] VSCode Plugin - Other

來到 VSCode Plugin 介紹的最後一天，想整理一些雖然跟開發沒直接相關，但是能幫助提升生產力，或是能適當幫助自己休息的工具。

## TODO Highlight

- [Github 連結](https://github.com/wayou/vscode-todo-highlight)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
- 推薦程度：⭐⭐⭐⭐

幫專案中有寫到`TODO`、`FIXME`等的關鍵字註解高亮起來，方便提醒開發者還有那些地方的程式碼等著我們去修改。

![png](https://github.com/wayou/vscode-todo-highlight/raw/master/assets/material-night-eighties.png)

## Todo Tree

- [Github 連結](https://github.com/Gruntfuggly/todo-tree)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
- 推薦程度：⭐⭐⭐⭐

顧名思義就是幫專案中有寫到`TODO`、`FIXME`等的關鍵字註解，依照檔案結構來產生樹狀的列表。

安裝完後 Todo Tree 會在編輯器左方新增一個面板，除了集中特定註解的好處，也可以點選後開啟特定檔案，相當方便。

![png](https://raw.githubusercontent.com/Gruntfuggly/todo-tree/master/resources/screenshot.png)

## Pomodoro Timer

- [Github 連結](https://github.com/lkytal/pomodoro)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=lkytal.pomodoro)
- 推薦程度：⭐⭐⭐⭐

唐鳳也愛用的蕃茄鐘，在 VSCode 也能用！

Pomodoro Timer 的功能很簡單，安裝之後會在下方功能列出現相關顯示。

![png](https://github.com/lkytal/pomodoro/raw/master/screenshot.png)

開始工作後，可以按播放鍵，就會顯示目前是 work 狀態，並倒數時間，預設是 25 分鐘。

![png](https://github.com/lkytal/pomodoro/raw/master/button.png)

25 分結束後，就會切換到 `rest`狀態，並倒數時間，預設是 5 分鐘。

![Imgur](https://i.imgur.com/cqsLU94.png)

當然可以到設定頁面針對個人的習慣調整時間和循環次數囉！

點選 Code > Preference > Settings，在 User tab 的 Extensions 找到 Pomodoro Timer，即可修改設定。

![Imgur](https://i.imgur.com/cuwLUD0.png)

## VSCode 批踢踢 (VSCode PTT)

- [Github 連結](https://github.com/Yukaii/vscode-ptt)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=Yukai.vscode-ptt)
- 推薦程度：⭐⭐⭐⭐

5 分鐘的休息時間，最適合來逛批踢踢啦！而且還不用另外開瀏覽器或 PCMan，不怕被老闆同事說閒話。

![gif](https://github.com/Yukaii/vscode-ptt/raw/master/docs/images/vscode-ptt-add-remove-board.gif)

![gif](https://github.com/Yukaii/vscode-ptt/raw/master/docs/images/vscode-ptt-open-article.gif)

## Stocks - Live Quotes

- [Github 連結](https://github.com/RanadeepPolavarapu/vscode-stocks)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=ranadeep.vscode-stocks-live)
- 推薦程度：⭐⭐⭐

看完批踢踢，有時間就可以來關心股票的漲跌囉！

安裝完後，這個工具需要需要以 iexcloud 取得股價資訊。先到[iexcloud](https://iexcloud.io/)這個網站註冊會員，然後拿到一組 API Token。

接著到設定頁面，前往 Stocks - Live Quotes 的區域，點選 Edit in Setting.json。

這時候就能依照自己需求輸入股號、更新頻率、API Token 以及顏色等。

```json
{
  "vscode-stocks.stockSymbols": ["GOOG", "MSFT", "AAPL", "AMZN"],
  "vscode-stocks.iexCloudAPIKeys": ["pk_95cf364f5XXXXXXXXXXXXX70XXXXX"],
  "vscode-stocks.colorStyle": ["#fd6e70", "#6cb33f", "white"],
  "vscode-stocks.useColors": true,
  "vscode-stocks.refreshInterval": 30000,
  "vscode-stocks.showChangeIndicator": true
}
```

![png](https://raw.githubusercontent.com/ranadeeppolavarapu/vscode-stocks/master/images/example.png)

## Music Time for Spotify

- [官網連結](https://www.software.com/music-time)
- [Github 連結](https://github.com/swdotcom/swdc-vscode-musictime)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=softwaredotcom.music-time)
- 推薦程度：?

在找文章的時候意外看到的工具，覺得很新鮮！

不過在試玩後，發現他不是直接在編輯器裡播放音樂，還是還要開啟 Spotify。而且在操作功能中，一直跳出 Premium 會員限定的訊息。

如果有人玩過覺得不錯用的話，再麻煩跟我分享喔！

## 參考資源

- [4 VS Code Extensions to “Slack off” at Work](https://medium.com/swlh/4-vs-code-extensions-to-slack-off-at-work-8de88c6ec793)
- [Visual Studio Code 必裝套件(extensions)](https://blog.typeart.cc/visual-studio-code-recommend-extensions/)
