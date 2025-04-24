# 臺灣 eduroam iDP RADIUS 伺服器憑證資料庫
- 這裡為產生 eduroam 設定檔時，伺服器傳送給客戶端的伺服器 CA 憑證檔，僅此而已。<br>
- 本資料庫將不定期更新，主要供研究人員使用。
<!--
如果有網管看到這邊，能的話確認一下貴校的 iDP 憑證狀態，憑證到期的記得續期，還在用 Example Certificate Authority 建議換掉。
如果不知道換哪家的，推薦可以換成 Let's Encrypt(免費，三個月效期) 或者 Buypass Go SSL(免費，六個月效期)，都可以用 Certbot 做 ACME 自動更新，讓你一輩子都不用為憑證續期發愁。
-->
## 檔案格式
- `(root_)<Realm>-<Method>-<Format>.<Format>`
    - Realm: @ 後面的網域 (eg: mail.edu.tw) (註，該欄位內容可與憑證內 CN 欄位值不同)
    - Method: 測試認證方式，目前有 `PEAP-MSCHAPv2`, `TTLS-PAP` 兩種方式，如果無檔案即代表伺服器未回傳憑證。
    - Format: DER(二進位編碼) 或 PEM(Base64)
    - 前方加上 `root_` 代表其為根憑證
