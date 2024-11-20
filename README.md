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
  - 資通安全管理法
    - 實施細則-罰則:
        - 公務機關10萬~100萬以下罰則,五年以下有期徒刑。 
        - 特並非公務機關5萬~50萬以下罰則,五年以下有期徒刑。 
        - 假借職務之權利罰則加重1/2。
        - 每人一事件賠償金額:500以上20000以下。
    - 資安應變及通報辦法(後續再討論)
    - 
  - 隱私權(包含以下法規):
    - GDPR(General Data Protection Regulation)
      - 範圍:在歐洲設廠之跨國廠商及歐盟在地廠商。
      - 目的:確保使用者可以自行控制個資之權利。
    - 個資法:
      - 特種個人資料包括犯罪前科,基因,醫療,性生活,病歷,健康檢查。
      - 使用個資須告知:目的,類別,使用期間,地區,單位名稱。
  - 智慧財產權:是一個廣泛的法律概念(包含以下法規)
    - 專利權法:保護技術發明。
    - 著作權法:保障創作者著作權與權力。
    - 營業秘密法:保護商業機密訊息。
    - 商標權法:保護商標,識別性標記。
- 資產管理
    - 資產清冊根據類別,職責與CIA來制定清冊
    - 類別與權責
      - 目的是使用分級制度來保護資訊資產方便管控及確保資料的機敏性。
      - 根據台灣法規,每個角色都要有明確分工及確切職責,職責不可重疊(不可以一個人有很多角色)!
      
      |角色|權責|確切職位|
      |------|--------|-----|
      |Owner(擁有者)|組織政策的制定權,組織方向界定,權限的分配權|專案負責人,經理,總監,部門主管,資訊長 (CIO),數位長 (CDO),首席風險官 (CRO),資訊安全長（CISO）|
      |Custodiam(保管者)|按照Owner分配權限來管理權限分配權限;維護數據的完整性和可用性;確保災難復原計畫可以快速響應|IT運維工程師|
      |User(使用者)|遵守組織的政策,發現組織的系統弱點須立即回報,只有資料的適當存取權,沒有任何異動之權利|開發人員,業務人員,外部廠商,部門主管|
      |Risk Owner(風險擁有者)|風險評鑑之權責,風險評估之權責,要承擔最後殘餘風險,緩解系統的安全性|首席資訊安官,風險管理主管|
      
- 風險管理
    - ISO27005風險管理流程
    - STEP1 | 全景建立 | :包括目標,範圍,參與人員等等。
    - STEP2 | 風險鑑別 | :根據CIA及法規遵循來風險評鑑。包括風險識別,風險分析(決定風險等級),風險評估。
    - STEP3 | 殘餘風險在確認 | :再次確認是否組織可以承受之風險。
    - STEP4 | 風險處理 | :風險轉移(買保險,丟給第三方),風險接受(為組織可接受之風險級別),風險降低,風險避免。
   
- 密碼學
  ```
  密碼學是用來確保數據的機密性和完整性
  ```
  - 現代密碼
    - 對稱式加密
      - DES(會被暴力破解),3DES(會被暴力破解),AES(最安全,支持三種密鑰長度：128 位、192 位、256 位)
    - 非對稱式加密
      - RSA（Rivest-Shamir-Adleman）,ECC（Elliptic Curve Cryptography)橢圓曲線密碼學,EdDSA（Edwards-Curve Digital Signature Algorithm）曲線數位簽章演算法
    - 雜湊函數
      - 是用來製作數位信封的加密技術
      - 單向加密,只可以加密不可解密
- 密碼學應用
    - 數位簽章(具有單向性,無法從雜湊值恢復原始數據及固定長度輸出之特性)
      - **STEP1 | 簽章生成 |** :使用雜湊函數(SHA-256,SHA-512)生成數據的雜湊值。
      - **STEP2 | 簽章驗證 |** :接收方使用傳送方之公鑰解密出雜湊值,在使用傳送方的雜湊函數來驗證是否一致
    - 數位信封(對稱式加密混合非對稱式加密)加解密流程
      - **STEP1 | 加密信件 |** :傳送方使用自己的私鑰加密數位信封的對稱式私鑰(例如:AES)。
      - **STEP2 | 加密對稱式私鑰 |** :傳送方使用接收方的公鑰來加密數位信封的對稱式私鑰。
      - **STEP3 | 傳送 |** :將加密後的傳送方私鑰與加密信封一起送至接收方。
      - **STEP4 | 解出對稱私鑰 |** :接收方使用自己的私鑰解出傳送者給的數位信封之對稱式私鑰。
      - **STEP5 | 開啟信封 |** :用傳送者的私鑰解開數位信封。
- 身分存取管理
    - 身份存取類型
      - **實體類**：監視器，門鎖
      - **技術類**：生物認證，防火牆系統，加解密技術
      - **管理類**：管理政策
    - 七大功能性身份存取管理
      - **赫阻性**:警語
      - **偵測性**：CCTV
      - **預防性**：門禁卡
    - AAA身份驗證模型
      - **Accounting(可歸責性）**：紀錄每個存取身份的所有存取動作。
      - **Authorization（授權）**：給予使用者權利。
      - **Authentication(鑑別原則）**：密碼、驗證碼。
    - 身份權限管理原則
      - **職位區隔**：不可以同一個人做很多事
      - **最小權限原則**：只授與職位的最小所有權限
      - **業務僅知原則**：只需要知道職位需要知道的事

- 身份驗證技術
   - **SNMP**:網管相關技術
   - 字典猜測攻擊關鍵字：paawordlist
   - 驗證技術安全指標
     - **FRR(Reject Rate)**:越高越安全。
     - **FAR(Accept Rate)**:越低越安全。
     - **CER( Crossover)**:FAR跟FRR的交會點，愈低愈安全。
- 備份管理
  - 備份方法
  
  |備份形式|備份速度|複雜程度|描述|
  |----|---|---|---|
  |完整備份|最慢|最簡單|最簡單但是需要備份最久,可獨立備份|
  |差異備份|中|中|相對增量備份簡單,速度比增量備份慢,需要依靠上一次的完整備份|
  |增量備份|最快|最複雜|複雜度最高,速隊最快需要依靠上一次的完整備份|
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
  - **SANS Incident Response System(舉例說明:如果一家公司正遭受網路攻擊)**
  
  | 階段| 說明|
  |----|---------|
  |Preparation|事先部屬的IDS(Intrusion Detection System),IPS(Intrusion Protection System)或SIEM(Security Information & Events Management)|
  |Identification|從SIEM系統,IDS及IPS發現入侵痕跡屬於偵測階段|
  |Containment|隔離伺服器與清除Malware遏制階段|
  |Eradication|修復系統漏洞|
  |Recovery|從Backup中還原系統資料屬於還原階段|
  |Lesson Learned|事後與團隊的檢討與討論屬於事件學習階段|
  
  - 通常發生資安事故後會根據法規來向執法單位報案,執行後續數位鑑識程序
  - 數位鑑識流程(針對取得證據) 
- 資安應變及通報辦法
  - 通報流程
    - **STEP1 | 入侵識別 |** 
    - **STEP2 | 內部通報 |**:可以使用任何形式(email,口頭,簡訊)來迅速通知權責單位。
    - **STEP3 | 紀錄細節 |**
    - **STEP4 | 啟動應變 |** 
    - **STEP5 | 深入調查 |**
    - **STEP6 | 災難復原計畫(BCP) |** 
    - **STEP7 | 結案報告 |**
  - 特殊情況須向執法單位通報(不算是通報流程)
    - 法律要求
    - 已經確認明確的網路犯罪
    - 由於風險轉移的申請保險理賠
  - 資安事件分級應變時間表
  |等級|針對對象及嚴重程度|通報時間|主管機關之審核時間|應變時間|
  |----|----|------|-----|-----|
  |第4級|國家公務機關之機密,敏感,核心業務之CIA| 1H|2H|36H|
  |第3級|一般公務機關之機密,敏感,核心業務之CIA|  1H|2H|36H|
  |第2級|非公務機關,非核心業務之CIA|  1H|8H|72H|
  |第1級|非公務機關,非核心業務之CIA| 1H|8H|72H|
- 營運持續
  - 災難復原計畫(BCP)
    - MRT(最大認售復原時間)
    - RTO(time復原時間)
    - RPO(point復原點)
  - 備援技術
    - 熱備援
    - 溫備援
    - 冷備援
  - 異地備援計劃之準則

  

  
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
    - 病毒類型
      - 蠕蟲(不須附著於惡意程式):區域網段掃描,自行裂變。
      - 木馬(需附著於惡意程式上):躲在盜版軟體當中是用來竊取資料,遠程控制,維持存取,製作殭屍網路的電腦病毒。
    - 免殺技術:病毒通常會夾帶免殺技術來躲避防毒軟體的規則,所以防毒軟體要常常更新!
     

- OWASP Top Ten Risks -2021 十大漏洞 | [網站攻擊手法](https://github.com/shawnhuang125/Cyber-Security/blob/main/web_attack.md) | [OWASP](https://owasp.org/)
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
- 協定安全 | HTTP+ SSL/TLS
    ```
    使用SSL/TLS加密技術讓網頁內容傳輸更加安全
    ```
    - SSL/TLS版本歷史
    ```
    SSL3.0---->TLS1.0---->TLS1.1---->TLS1.2---->TLS1.3(目前TLS最新版本為1.3)
    ```
    - 現代加密標準
    - AES-138,AES-256,SHA-256
    - 已被淘汰的加密標準
    - RC4,DES,3DES,SSL,SHA-1 哈希算法,RSA密鑰交換


- 作業系統安全

- 應用程式安全

- 開發安全
  - SSDLC

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

- 日誌管理
  ```
  日誌得紀錄是為了確保誰做了甚麼(可歸責性Accountability)及確保行為的不可抵賴性(不可否認性)。
  ```
    
    - 日誌蒐集與分析之準則
      - **Data Normalization資料正規化**:統一格式化,便於分析
      - **Data Cleaning資料清洗**:刪除不必要的內容,便於分析
      - **clock Synchronization時間同步**:確保每個日誌檔的準確性
  
    - 日誌存放路徑(日誌要壓縮留存,日誌集中儲存於Log Server)

      |日誌類型|日誌存放路徑|
      |---|---|
      |SSH,FTP,POP3,TELNET|`var/log/secure`|
      |登入者訊息|`var/log/wtmp`|
      |紀錄開機|`var/log/boot.log`|



