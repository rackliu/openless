# OpenLess 使用指南

## 安裝

### macOS

1. 從 [Releases](https://github.com/appergb/openless/releases/latest) 下載 `OpenLess_<版本>_aarch64.dmg`。
2. 開啟 dmg，將 OpenLess.app 拖入「應用程式」資料夾。
3. 雙擊啟動。

### Windows

1. 從 [Releases](https://github.com/appergb/openless/releases/latest) 下載 `OpenLess_<版本>_x64-setup.exe`。
2. 執行安裝程式，按提示完成安裝。
3. 從開始選單啟動 OpenLess。

---

## 首次配置

### macOS 許可權

首次啟動後，在「系統設定 → 隱私與安全」中授予以下許可權：

1. **麥克風** — 允許 OpenLess 錄音。
2. **輔助功能** — 允許 OpenLess 讀寫當前焦點輸入框。授權後須**完全退出並重新啟動** OpenLess，快捷鍵才會生效。

### Windows 許可權

1. 按系統提示授予**麥克風**許可權。
2. 開啟 OpenLess → 「設定 → 許可權」，確認全域性快捷鍵監聽器狀態顯示為「已啟動」。

### 填入憑據

不會配火山 ASR 的話，先看這篇圖文引導：  
[OpenLess 火山 ASR 配置](docs/volcengine-setup.md)

開啟 OpenLess → **設定**，填入以下欄位：

| 欄位 | 說明 |
| --- | --- |
| 火山引擎 App ID | 語音識別服務的應用 ID |
| 火山引擎 Access Token | 語音識別訪問憑據 |
| 火山引擎 Resource ID | 語音識別資源 ID |
| Ark API Key | 文字潤色服務的 API Key |
| Ark Model ID | 使用的模型 ID（如 `doubao-pro-32k`） |
| Ark Endpoint | 介面地址，預設 `https://ark.cn-beijing.volces.com/api/v3/chat/completions` |

儲存後設置立即生效，無需重啟。

---

## 本地模型配置建議

如果你想把 OpenLess 配成“本地 ASR + 本地大語言模型潤色”的組合，建議先明確目標：這裡追求的不是通用問答能力，而是**短句口語整理、低延遲、中文 / 中英混輸穩定度**。模型選擇時，優先看首字延遲、斷句自然度和指令服從性，而不是隻看引數量。

### 硬體建議

- 若要同時執行本地 ASR 和本地大語言模型，建議至少有 **8GB 顯示卡視訊記憶體**。
- 低於這個級別通常仍可執行部分輕量模型，但更容易出現模型載入慢、首字延遲高、切換場景後體感不穩定等問題。

### 本地 ASR 怎麼選

- **Windows 11**：優先使用 **Foundry Local Whisper**。
- **Windows 11 當前不建議把 Qwen3-ASR 當作主力路徑**。
- 如果你的目標是“先穩定跑起來”，先把本地 ASR 路徑單獨測通，再接本地大語言模型做潤色。

### 本地大語言模型怎麼選

- 如果你的本地推理工具提供 **OpenAI 相容 endpoint**，OpenLess 可以直接接入這個 endpoint 做潤色。
- 對 8GB 級別顯示卡來說，建議優先選擇 **7B 到 9B 的 instruct 模型**，並使用 **4-bit 或同級量化**。

建議順序如下：

1. **中文優先**：優先嚐試 **Qwen 系 7B 到 9B instruct 模型**。
2. **速度優先**：可先從 **Gemma 4 e4b** 開始。
3. **更保守的輕量起點**：可先試 **Gemma 4 e2b**，適合驗證整條本地潤色鏈路是否可用。

當前已做過的簡單測試模型包括：`gemma-4-e4b`、`gemma-4-e2b`、`qwen3.5-9b`。

### 不建議的做法

- 不建議一開始就追更大的本地大語言模型。對 OpenLess 這種即時語音輸入工具來說，過大的模型往往只會明顯拉高首字延遲，日常體驗下降通常比質量提升更明顯。
- 不建議預設開啟“思考”模式。OpenLess 的主要任務是整理文字，不是長推理或多步任務規劃。

### 建議的預設調校

如果你想先得到一組容易落地的配置，可以從下面開始：

1. ASR：Foundry Local Whisper
2. LLM：Qwen 系 7B 到 9B instruct，或 Gemma 4 e4b
3. 量化：4-bit 優先
4. 思考模式：關閉
5. 上下文視窗：先保持較小，不要一開始拉太大
6. 用途：短句口語整理、Prompt 潤色、郵件 / 文件改寫

---

## 基本使用

### 開始錄音

按下全域性快捷鍵（預設 macOS 右 Option，Windows 右 Control）。  
螢幕邊緣會出現狀態膠囊，顯示「錄音中」。

### 結束錄音

再次按下同一快捷鍵。OpenLess 會：

1. 停止錄音併發送音訊進行轉寫。
2. 對轉寫結果按當前輸出模式進行潤色。
3. 將潤色後的文字插入當前焦點輸入框（失敗時自動複製到剪貼簿）。

### 取消錄音

錄音過程中按 `Esc`，當前錄音內容會被丟棄，不做任何插入。

---

## 輸出模式

在 OpenLess 主視窗的膠囊或「設定」中切換模式：

| 模式 | 說明 |
| --- | --- |
| 原文 | 直接輸出轉寫文字，不做任何修改 |
| 輕度潤色 | 修正語氣詞、標點、明顯錯字，保留原意 |
| 清晰結構（AI prompt 模式） | 把口語整理成有結構、有約束、有上下文的 prompt，適合直接餵給 ChatGPT / Claude / Cursor |
| 正式表達 | 將口語轉換為正式書面語 |

---

## 詞典

詞典用於提高特定詞彙的識別準確率（產品名、人名、專有名詞等）。

1. 開啟主視窗 → **詞典**。
2. 點選「新建」，填入正確拼寫、分類和備註。
3. 啟用後，詞條會作為熱詞注入 ASR 識別階段，並在潤色階段輔助語義判斷。

---

## 歷史記錄

主視窗 → **歷史**，可檢視所有錄音記錄，包括原始轉寫和潤色結果。

---

## 更換快捷鍵

主視窗 → **設定 → 快捷鍵**，選擇觸發鍵。  
macOS 支援右側修飾鍵（Option / Control / Command / Shift）；Windows 支援右 Control。

---

## 常見問題

**Q: 快捷鍵沒反應？**  
macOS：確認已授予輔助功能許可權，且授權後重啟過 OpenLess。  
Windows：在「設定 → 許可權」中檢查監聽器狀態。

**Q: 識別結果為空或是佔位文字？**  
檢查火山引擎 ASR 憑據是否填寫正確。填寫正確後識別才能正常工作。

**Q: 文字沒有插入，只是複製到了剪貼簿？**  
當目標輸入框不支援輔助功能寫入時（如某些安全限制的應用），OpenLess 會自動回退到剪貼簿複製，手動貼上即可。

**Q: 在 Windows 玩 Minecraft 等全屏遊戲時，OpenLess capsule 不彈出 / 字元無法輸入？**  
這是 **Windows 作業系統層面的限制**，OpenLess 應用本身無法繞過（詳見 [issue #457](https://github.com/Open-Less/openless/issues/457)）：

- **獨佔全屏（exclusive fullscreen）**：標準應用視窗（包括 OpenLess capsule）**不會繪製在獨佔全屏 DirectX/OpenGL 應用之上**。請把遊戲切換到 **無邊框視窗化全屏（Borderless Windowed Fullscreen）**。Minecraft：影片設定 → 全屏 關閉（保持視窗最大化即可）。
- **管理員許可權不一致（UIPI）**：若遊戲以管理員身份執行而 OpenLess 不是，Windows 阻止 OpenLess 接收遊戲前臺的按鍵，hotkey 完全不觸發。讓兩者許可權對齊（要麼都以管理員執行，要麼都以普通使用者執行）。
- **遊戲聊天框未開啟**：識別字符透過模擬鍵盤事件落字。Minecraft 中必須先按 `T` 開啟聊天框，OpenLess 的輸入才會落到聊天裡。

macOS 不存在獨佔全屏（所有"全屏"都是帶 Spaces 的無邊框視窗），所以此限制不適用。

**Q: 潤色結果和預期不符？**  
嘗試切換輸出模式，或在詞典中新增相關專有名詞。

---

## 社群與支援

歡迎透過 QQ 加入使用者群，反饋問題或交流使用體驗：

**QQ 群：1078960553**
