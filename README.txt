心聊 ChatMate v6（C 方案介面）

檔案：
- index.html：網站介面與離線範本
- manifest.json：PWA 設定
- sw.js：離線快取（v6）
- README.txt：本說明

本版差異：
1. 智慧回覆維持快速的內建範本推薦。
2. 高情商教練有獨立的目標與背景欄位，會輸出「情境分析、建議策略、回覆建議、溫柔提醒」。
3. 未設定 AI 服務時，教練使用本機規則式引導，會清楚標示「本機引導模式」，不會假稱是真正 AI。
4. 可在教練模式的「進階」中設定安全後端 API 網址。網址儲存在本機瀏覽器。

重要：真正的 AI 服務尚未自動連接。需要先部署一個 HTTPS 後端服務，並由後端保管 AI API 金鑰。請勿把 API 金鑰直接放進 index.html、公開 GitHub 或前端程式。

後端契約：
- 請求：POST JSON {"message":"...","goal":"...","context":"...","tone":"..."}
- 回應：JSON {"analysis":"...","strategy":"...","replies":["回覆一","回覆二","回覆三"],"caution":"..."}
- 後端需允許此 GitHub Pages 網站來源的 CORS 請求，並使用 HTTPS。

更新 GitHub Pages：
1. 將這四個檔案上傳到專案根目錄（不要把資料夾或 ZIP 當成網站根目錄）。
2. 如果 GitHub 詢問是否覆蓋 index.html、sw.js 等既有檔案，選擇覆蓋／Commit changes。
3. 確認 Pages 仍使用 main 分支與 /(root)。
4. 部署完成後重新整理網站；若仍是舊版，關閉後重新開啟，或清除網站快取。

隱私提醒：本機記憶及 AI 服務網址儲存在目前瀏覽器的 localStorage。連接 AI 服務後，送出的訊息會傳到妳設定的後端；請勿輸入密碼、身分證號等敏感資料。
