# http狀態碼列表
### 1xx: Informational Responses
- 1xx 代碼表示請求已被接收，繼續處理中。

- 100 Continue: 伺服器收到請求的初步部分，客戶端可以繼續。
- 101 Switching Protocols: 客戶端請求的協議升級（例如切換到 WebSocket）。
- 103 Early Hints: 提示客戶端一些資源的加載，改善性能。
### 2xx: Success
- 2xx 代碼表示請求已成功處理。

- 200 OK: 請求成功，通常用於 GET 和 POST。
- 201 Created: 資源已成功創建，通常用於 POST。
- 202 Accepted: 請求已接受，但尚未處理完成。
- 204 No Content: 請求成功，但沒有返回任何內容（例如 DELETE 操作）。
- 206 Partial Content: 返回部分內容（用於 HTTP 範圍請求，如文件下載）。
### 3xx: Redirection
- 3xx 代碼表示需要進一步操作以完成請求。

- 300 Multiple Choices: 多個可能的資源供選擇。
- 301 Moved Permanently: 資源永久轉移到新位置（SEO 中重要）。
- 302 Found: 資源暫時轉移（通常用於臨時重定向）。
- 303 See Other: 重定向到另一資源，通常用於 POST 結果的 GET。
- 304 Not Modified: 資源未更改，客戶端可以使用緩存。
- 307 Temporary Redirect: 資源臨時重定向（請求方法保持不變）。
- 308 Permanent Redirect: 資源永久重定向（請求方法保持不變）。
### 4xx: Client Errors
- 4xx 代碼表示客戶端請求錯誤。

- 400 Bad Request: 請求無效或語法錯誤。
- 401 Unauthorized: 未經授權，需提供身份驗證。
- 403 Forbidden: 伺服器拒絕執行請求（例如權限不足）。
- 404 Not Found: 找不到請求的資源。
- 405 Method Not Allowed: 請求方法不被允許（例如用 GET 訪問需要 POST 的路徑）。
- 406 Not Acceptable: 客戶端要求的 MIME 類型無法被伺服器滿足。
- 408 Request Timeout: 請求超時。
- 409 Conflict: 請求與伺服器的資源狀態衝突。
- 410 Gone: 資源永久不可用。
- 413 Payload Too Large: 請求體過大。
- 414 URI Too Long: 請求 URI 過長。
- 415 Unsupported Media Type: 不支持的媒體類型。
- 429 Too Many Requests: 請求過多（通常用於速率限制）。
### 5xx: Server Errors
- 5xx 代碼表示伺服器錯誤。

- 500 Internal Server Error: 通用伺服器錯誤，無法處理請求。
- 501 Not Implemented: 伺服器不支持請求方法。
- 502 Bad Gateway: 作為網關的伺服器收到無效響應。
- 503 Service Unavailable: 伺服器無法處理請求（通常是過載或維護）。
- 504 Gateway Timeout: 作為網關的伺服器未能在預期時間內收到響應。
- 505 HTTP Version Not Supported: 不支持的 HTTP 協議版本。
