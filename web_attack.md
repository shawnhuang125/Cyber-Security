# OWASP Top Ten Risks -2021 十大漏洞 
```
OWASP是一個幫助開發者了解WEB的開發漏洞的非營利性開放社群組織。
```

  | 弱點(vulnerability) |層級|攻擊手法|防範|
  |----------|---|---|---|
  |權限控制失效 (Broken Access Control)|`Application layer`|（Horizontal Privilege Escalation):查看其他用戶資訊,垂直權限提升（Vertical Privilege Escalation):嘗試訪問管理員權限|每次的訪問中每個使用者都需要至後端驗證權限水平權限提升|
  |加密機制失效 (Cryptographic Failures)|`Presentation layer`,`Application layer`|攻擊者劫持未經加密的數據傳輸(HTTP)或破解數據的弱密碼(MD5,SHA-1 Hashi)|使用https傳輸,使用AES-256,SHA-256加密|
  |注入式攻擊 (Injection)|`Application layer`|sql注入:再輸入欄位中插入sql查詢,command注入:插入系統指令操作伺服器|確實檢查前端輸入的正確性,使用參數化的SQL查詢結合API至後端執行查詢,設置WEB應用防火牆|
  |不安全設計 (Insecure Design)|`Application layer`|易遭受結構化攻擊|需要威脅建模及[安全測試](https://github.com/shawnhuang125/Penetration-Testing)|
  |安全設定缺陷 (Security Misconfiguration)|`Application layer`|使用默認的帳號密碼,開啟必要的服務及端口|關閉讀必要的服務及端口,定期檢查服務配置|
  |危險或過時的元件 (Vulnerable and Outdated Components)|`Application layer`|利用已被發現的漏洞對未更新的資源庫或系統攻擊|定期更新系統及資源庫|
  |認證及驗證機制失效 (Identification and Authentication Failures)|`Application layer`|暴力破解|嚴格執行強密碼策略,限制密碼錯誤次數|
  |軟體及資料完整性失效 (Software and Data Integrity Failures)|`Application layer`|供應鏈攻擊,植入木馬|採用可被信任的資源庫|
  |資安記錄及監控失效 (Security Logging and Monitoring Failures)|`Application layer`|攻擊者利用沒有日誌與監控來掩蓋其入侵行為|增設日誌及安全監控|
  |伺服端請求偽造 (Server-Side Request Forgery)|`Application layer`|繞過防火牆直接存取內部資源|增設防火牆.驗證內部與外部的請求|

# 網站攻擊手法介紹
### SQL Injecting資料庫注入攻擊
### COMMAND Injecting命令注入攻擊
### XSS攻擊

