# [Day22] Windows 切換 NodeJS 版本 - NVM

## 前言

前幾天在拉公司的專案時，不知為何 npm 一直安裝失敗，嘗試了各種方法也沒成功。所幸想試試切換 NodeJS 的版本來看看。

剛開始還在苦惱說 Windows 是不是沒有像 for macOS 的 nvm([Node Version Manager](https://github.com/creationix/nvm))，沒想到很快就找到啦！

## 安裝

首先，先到這個[Github 的 release](https://github.com/coreybutler/nvm-windows/releases)中下載檔案，我是選擇`nvm-setup.zip`以執行檔的方式安裝。

完成後，打開 cmd 輸入`nvm`，成功的話就會出現相關的 help 提示。ㄇ

## 常用指令

- `nvm install latest`：安裝最新版本的 NodeJS
- `nvm install X.X.X 32/64`：安裝 X.X.X 32 或 64 位元的版本
- `nvm list`：列出所有版本的 NodeJS
- `nvm use X.X.X`：切換到 X.X.X 版本的 NodeJS

![Imgur](https://i.imgur.com/yCH06rA.png)

## 官方文件

- [Github - nvm-windows](https://github.com/coreybutler/nvm-windows)

## 參考文章來源

- [How to run multiple versions of NodeJS with nvm for Windows](https://medium.com/appseed-io/how-to-run-multiple-versions-of-node-js-with-nvm-for-windows-ffbe5c7a2b47)
