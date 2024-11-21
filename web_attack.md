# OWASP Top Ten Risks -2021 十大漏洞 
```
OWASP是一個幫助開發者了解WEB的開發漏洞的非營利性開放社群組織。
```

  | 弱點(vulnerability) |描述|
  |----------|----|
  |權限控制失效 (Broken Access Control)|沒有確切驗證使用者身分。|
  |加密機制失效 (Cryptographic Failures)|沒有使用高安全性之加密技術所以http連線易被駭客劫持。|
  |注入式攻擊 (Injection)|沒有嚴格驗證前端的輸入資訊造成伺服器資訊被洩漏。|
  |不安全設計 (Insecure Design)|沒有考量網站安全性的設計,易造成網站很多層面的漏洞。|
  |安全設定缺陷 (Security Misconfiguration)|沒有確認系統或系統套件或資料庫有配置上的是否正確配置。|
  |危險或過時的元件 (Vulnerable and Outdated Components)|沒有定期更先系統套件版本以修補漏洞。|
  |認證及驗證機制失效 (Identification and Authentication Failures)|沒有嚴格確認使用者的存取身分造成資料完整性破壞。|
  |軟體及資料完整性失效 (Software and Data Integrity Failures)|沒有定期更先系統配件與資料庫版本進行漏洞修補。|
  |資安記錄及監控失效 (Security Logging and Monitoring Failures)|沒有確認日誌與監控是否完整配置。|
  |伺服端請求偽造 (Server-Side Request Forgery)|沒有嚴格確認造訪者請求的存取身分。|

# 網站攻擊手法介紹
### 權限控制失效 (Broken Access Control)
### 加密機制失效 (Cryptographic Failures)
### 注入式攻擊 (Injection)
- **SQL Injection (SQL注入)**
  - 實例： 場景：網站登入功能。 輸入框的SQL查詢如下：

  ```
  SELECT * FROM users WHERE username = '$username' AND password = '$password';
  ```
- 攻擊者輸入：
  ```
  Username: ' OR '1'='1
  Password: ' OR '1'='1
  ```
- 結果生成的SQL查詢：
  ```
  SELECT * FROM users WHERE username = '' OR '1'='1' AND password = '' OR '1'='1';
  ```
- 這會使查詢永遠為真，攻擊者成功繞過身份驗證，進入系統。
- **Command Injection (命令注入)**
  - 實例： 場景：Web應用允許用戶透過輸入IP地址來Ping伺服器。 後端代碼：
  ```
  ping -c 4 $user_input
  ```
- 攻擊者輸入：

  ```
  127.0.0.1; rm -rf /
  ```
- 結果生成的命令：

  ```
  ping -c 4 127.0.0.1; rm -rf /
  ```
  - 這會導致系統執行rm -rf /，刪除伺服器的所有檔案。


### 不安全設計 (Insecure Design)
### 安全設定缺陷 (Security Misconfiguration)
### 危險或過時的元件 (Vulnerable and Outdated Components)
### 認證及驗證機制失效 (Identification and Authentication Failures)
### 軟體及資料完整性失效 (Software and Data Integrity Failures)
### 資安記錄及監控失效 (Security Logging and Monitoring Failures)
### 伺服端請求偽造 (Server-Side Request Forgery)

