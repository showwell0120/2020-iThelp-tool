# [Day28] VSCode Plugin - Debug Visualizer

- [Github 連結](https://github.com/hediet/vscode-debug-visualizer)
- [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=hediet.debug-visualizer)
- [Playground](https://hediet.github.io/visualization/?darkTheme=1&tsTypes=1)
- 推薦程度：⭐⭐⭐

在 VSCode 除錯，除了可以進行基本的中斷點設定，來觀察變數的數值變化以外，現在還有位神人，開發一個能將變數的資料視覺化的工具。而且呈現的圖表跟結構非常多樣，也可以在除錯過程中動態展示資料的變化，相當的神奇。

不過由於他的功能太過強大，因此需要點時間熟悉對應指令，以及環境的建立。一開始可以先去 Playground 玩玩看有哪些圖表呈現。或者可以先 clone 專案下來練習看看。

目前該工具支援度最高的語言是 Javascript 跟 Typescript。我們先用 VSCode 打開 `demos/js`目錄來試玩看看。

在執行除錯前有幾個前置步驟 -

1. `yarn install`安裝依賴
2. 在 `.vscode/`目錄新增 launch.json
   ```json
   {
     // 使用 IntelliSense 以得知可用的屬性。
     // 暫留以檢視現有屬性的描述。
     // 如需詳細資訊，請瀏覽: https://go.microsoft.com/fwlink/?linkid=830387
     "version": "0.2.0",
     "configurations": [
       {
         "type": "node",
         "request": "launch",
         "name": "Launch Program",
         "skipFiles": ["<node_internals>/**"],
         "program": "${workspaceFolder}\\src\\demo_doubly-linked-list.ts",
         "preLaunchTask": "tsc: build - tsconfig.json",
         "outFiles": ["${workspaceFolder}/dist/**/*.js"]
       }
     ]
   }
   ```
3. 在 `.vscode/tasks.json`的`tasks`列表新增以下物件 -
   ```json
   {
     "type": "typescript",
     "tsconfig": "tsconfig.json",
     "problemMatcher": ["$tsc"],
     "group": "build",
     "label": "tsc: build - tsconfig.json"
   }
   ```

完成後，我們到 launch.json 設定的 `program`路徑 - `demo_doubly-linked-list.ts`下中斷點。

接著就可以按**F5**執行除錯功能。跑起來後再按**F1**開啟指令列，輸入 `Debug Visualizer: New View`，就能開啟 Debug Visualizer 的顯示頁面。

當跑到中斷點後，在 Debug Visualizer 的輸入列打 `visualize()`，就能看到 list 的資料結構被視覺化了。

![gif](https://github.com/hediet/vscode-debug-visualizer/raw/master/docs/demo.gif)

另外不只靜態資料的變數可以顯示，連非同步回傳的資料也可以。把 launch.json 的 `program`設為 `demo_fetch.js`，再重新執行除錯。

當跑到中斷點後，在 Debug Visualizer 的輸入列打 `json`，就能以清楚明瞭的表格查看 API 回傳的資料。

![gif](https://i.imgur.com/ISquxhq.gif)

以下的參考資源，還有人整理更多應用跟使用教學，有興趣的可以再前往看看喔!

## 參考資源

- [Visualize Data Structures in VSCode](https://addyosmani.com/blog/visualize-data-structures-vscode/?fbclid=IwAR1Sm3BBLsV0Enh89aitWeMkcvFN2YMgTUAt5qPG7_d0I4elsu9ajaWH3mEhttps://marketplace.visualstudio.com/items?itemName=ranadeep.vscode-stocks-live&fbclid=IwAR1SC_VYhhT4KtworrYzQndrJFcv7BW7bmqg2qifu9c4JA3tiG9I6HhLbRc)
- [Plotly JavaScript Open Source Graphing Library](https://plotly.com/javascript/)
