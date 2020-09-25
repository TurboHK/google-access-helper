<p align="center"><img width="15%" src="icons/icon-128.png" /></p>
<h1 align="center">谷歌訪問助手</h1>

最簡單易用的Google訪問助手,為Chrome用户量身打造。繁體中文全翻譯，極大方便繁體使用者。可解决Chrome在中國大陸境内無法自動更新擴充功能的問題，同時可以訪問Google服務。繁體中文版由TurboHKG翻譯。

<table align="center">
  <tr>
    <td align="center"><img src="img/google.png" /></td>
    <td align="center"><img src="img/chrome.png" /></td>
    <td align="center"><img src="img/gmail.png" /></td>
    <td align="center"><img src="img/googleplus.png" /></td>
  </tr>
  <tr>
    <td align="center">Google搜索</td>
    <td align="center">Chrome商店</td>
    <td align="center">Gmail郵箱</td>
    <td align="center">Google+</td>
  </tr>
</table>

**本擴充功能已破解，可永久免費使用！ **

## 安裝說明

由於新版本Chrome已禁止安裝第三方應用，且本破解版無法上傳至[Chrome網上應用店](https://chrome.google.com/webstore)，因此只能透過以下方法在開發者模式下運行：

1. 克隆本倉庫到本地或下載[master.zip](繁體中文版：https://github.com/TurboHK/google-access-helper/archive/master.zip，簡體中文版：https://github.com/haotian-wang/google-access-helper/archive/master.zip)後解壓縮
2. 打開Chrome擴充功能頁面 `chrome://extensions`
3. 勾選`開發者模式`
4. 點擊`加載已解壓的擴展程序`，選擇本擴充功能所在目錄

此外，也可以通過將本擴充功能添加至Chrome白名單的方式安裝，詳情請見[Wiki](https://github.com/haotian-wang/google-access-helper/wiki/Installation-Guide#%E5 %B0%86%E6%8F%92%E4%BB%B6%E5%8A%A0%E5%85%A5chrome%E7%99%BD%E5%90%8D%E5%8D%95)。

## 破解說明

- 該擴充功能的核心原始碼為[bg.js](bg.js)。該檔案已做代碼混淆和壓縮，本破解版已對該檔案進行格式化。

- 該擴充功能會在Chrome啟動時檢測打開的標籤頁是否包含推廣網站，以此判斷用戶是否將推廣網站設置為首頁。因此，只需在檢測標籤頁網址的代碼上強行加入推廣網站的地址，即可讓該插件認為已將其添加為首頁，不受12小時試用時間的限制。

  ```javascript
  a.links.push("http://360.hao245.com");
  a.links.push("http://123.hao245.com");
  a.links.push("chrome://newtab/");
  ```

- 該擴充功能透過代理服務器訪問Google，代理伺服器的位址和密碼以及PAC腳本均由插件動態獲取。研究發現，即使將PAC腳本替換掉，依然只能訪問Google網站，其餘網站無法打開，表明伺服器端已進行了限制。
