# 網路安全Cyber-Security
## 管理概論
- ISMS(Information Security Management System)
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
  - 安全事件分級制度  
  - 資安通報流程
## 技術概論

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

- OWASP Top 10 最常見的網路攻擊手法及其威脅

- 網路安全防護設備介紹

|  系統名稱  |IDS(Intrusion Detection System) | IPS(Intrusion Prevention System)   | WAF(Web Application Firewall)  | SIEM(Security Information & Events Management) | 
|-----------|----|---|---|----|
|用途|偵測用的系統|防禦用的系統|有偵測也有防禦|將來自各層的事件與事故全部整合並記錄下來|
|OSI層級|`Network Layer`|`Network Layer`|`Application Layer`|`整合多層數據`|


- 作業系統安全

- 應用程式安全

- 開發安全
  - SSDLC

- 備份管理
