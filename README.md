# 網路安全Cyber-Security
## 管理概論
- ISMS(Information Security Management System)
  -PDCA Cycle
  
  |執行階段|執行控制|
  |--------|--------|
  |Plan|確認範圍,領導承諾,|
  |Do|風險控制,風險評鑑|
  |Check|稽核,|
  |Active|實施|
  
- Law
  - 資通安全法
  - GDPR(General Data Protection Regulation)
  - 智慧財產權
  - 隱私權
- 資產管理
- 風險管理
- 密碼學
- 身分管理
- 備份管理
  - 備份方法
  
  |備份形式|備份速度|複雜程度|描述|
  |----|---|---|---|
  |完整備份|最慢|最簡單|可以單獨備份|
  |差異備份|中|中|需要依靠上一次的完整備份|
  |增量備份|最快|最複雜|需要依靠上一次的完整備份|
  ```
              (星期)(日)  (日)
  |------------|-----|-----|
          完整備份 差異備份 差異備份
  ```
  ```
              (星期)(日)  (日)
  |------------|-----|-----|
          完整備份 增量備份 增量備份
  ```
- 事件與事故管理(事件:未造成損失,事故:已造成損失)
  - 營運持續計畫SIEM(Security Information & Events Management)
  - SANS Incident Response System(舉例說明:如果一家公司正遭受網路攻擊)
  
  | 階段| 說明|
  |----|---------|
  |Preparation|事先部屬的IDS(Intrusion Detection System),IPS(Intrusion Protection System)及SIEM(Security Information & Events Management)|
  |Identification|從SIEM系統,IDS及IPS發現入侵痕跡屬於偵測階段|
  |Containment|隔離伺服器與清除Malware遏制階段|
  |Eradication|修復系統漏洞|
  |Recovery|從Backup中還原系統資料屬於還原階段|
  |Lesson Learned|事後與團隊的檢討與討論屬於事件學習階段|
  
  - 通常發生資安事故後會根據法規來向執法單位報案,執行後續數位鑑識程序
  - 數位鑑識流程(針對取得證據) 
  - 資安通報與應變
  
  |等級|針對對象及嚴重程度|通報時間|主管機關之審核時間|應變時間|
  |----|----|------|-----|-----|
  |第4級|國家公務機關之機密,敏感,核心業務之CIA| 1H|2H|36H|
  |第3級|一般公務機關之機密,敏感,核心業務之CIA|  1H|2H|36H|
  |第2級|非公務機關,非核心業務之CIA|  1H|8H|72H|
  |第1級|非公務機關,非核心業務之CIA| 1H|8H|72H|
  - 舉例說明
  - ![image](https://github.com/user-attachments/assets/9efb31a7-abf9-4d3c-8859-84846c164a9e)

  

  
## 技術概論
- 網路概論
  - 計算機網路-OSI

  |模型層級|功能|
  |---------|-----|
  |application layer|通訊協定,DNS解析|
  |presentation layer|加密解密,轉換格式|
  |session layer|通訊連線|
  |transport layer|切割數據段,附上序號,封裝數據包,|
  |network layer|路由協定,IP協定,防火牆,多層交換器|
  |data link layer|交換器VLAN協定,STP生成樹協定,AP,橋接器|
  |physical layer|MAC Address,網線,集線器hub|

  - TCP/IP協議默認端口

  |通訊協定|功能| Transport Layer|端口Portocol|
  |---------|---------|---------|---------|
  |HTTP(Hyper-Text Transport Portocol)|網頁造訪,數據不會加密|`TCP`|`80`|
  |HTTPS(Hyper-Text Transport Portocol Secure)|網頁造訪,數據會被加密|`TCP`|`443`|
  |SMTP(Simple Mail Transport Portocol)|EMAIL的傳輸協定|`TCP`|`25`|
  |IMAP(Internal Mail Accessible Portocol)|比較複雜的EMAIL的傳輸協定|`TCP`|`143`|
  |FTP(File Transport Portocol)|檔案的傳輸|`UDP/TCP`|`20/21`|
  |SSH(Secure Shell)|遠程造訪服務|`TCP`|`22`|
  |微軟網路芳鄰（NetBIOS over TCP/IP）|本地端訪問其他電腦,打印機,文件夾的默認通訊port|`TCP`,`UDP`|`137`,`138`,`139`|

  - 三向交握 
  - ![image](https://github.com/user-attachments/assets/0fa8cb0e-201e-482d-83d0-cc751eb21621)

- 惡意軟體(Malware)

- OWASP Top Ten Risks -2017 | [OWASP](https://owasp.org/)
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

- 網路安全防護設備介紹

  |系統名稱|用途|OSI層級|
  |-----------|----|---|
  |IDS(Intrusion Detection System)|一個用來偵測的防護裝置|`Network Layer`|
  |IPS(Intrusion Prevention System)  |一個用來防護的防護裝置|`Network Layer`|
  |WAF(Web Application Firewall) |一個用來偵測和防禦的防護裝置|`Application Layer`|
  |SIEM(Security Information & Events Management) |一個用來整合IDS和IPS的防護系統|`Application Layer`,`Network Layer`|
  |應用代理(Gateway)防火牆 |用來查看目標ip,限制特定的內對外連線|`Application Layer`|
  |狀態防火牆 |用來追蹤連線狀態的防火牆|`Network Layer`|
  |封包過濾防火牆|不檢查封包上層資料,通常防火牆規則較簡單|`Network Layer`|
- 協定安全

- 作業系統安全

- 應用程式安全

- 開發安全
  - SSDLC

- 備份管理

- 日誌管理
```
日誌得紀錄是為了確保誰做了甚麼(可歸責性Accountability)及確保行為的不可抵賴性(不可否認性)。
```
  - 日誌蒐集與分析之準則
    - Data Normalization資料正規化:統一格式化,便於分析
    - Data Cleaning資料清洗:刪除不必要的內容,便於分析
    - clock Synchronization時間同步:確保每個日誌檔的準確性
  
  - 日誌存放路徑(日誌要壓縮留存,日誌集中儲存於Log Server)

  |日誌類型|日誌存放路徑|
  |---|---|
  |SSH,FTP,POP3,TELNET|`var/log/secure`|
  |登入者訊息|`var/log/wtmp`|
  |紀錄開機|`var/log/boot.log`|



