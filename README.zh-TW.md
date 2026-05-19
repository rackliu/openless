<p align="center">
  <img src="openless-all/app/src-tauri/icons/128x128@2x.png" alt="OpenLess" width="160" />
</p>

<h1 align="center">OpenLess</h1>

<p align="center">
  <strong>開源語音輸入，支援 macOS 和 Windows。</strong><br/>
  按一次快捷鍵說話，AI 潤色後的文字直接落到當前游標。
</p>

<p align="center">
  <a href="https://openless.top"><strong>🌐 官方網站 — openless.top</strong></a>
</p>

<p align="center">
  <a href="README.md">English</a> · <a href="README.zh.md">简中</a> · <a href="README.zh-TW.md">繁中</a>
</p>

<p align="center">
  <a href="https://github.com/appergb/openless/releases/latest"><img alt="release" src="https://img.shields.io/github/v/release/appergb/openless?style=flat-square&color=2c5282" /></a>
  <a href="https://github.com/appergb/openless/blob/main/LICENSE"><img alt="license" src="https://img.shields.io/github/license/appergb/openless?style=flat-square&color=2f855a" /></a>
  <img alt="macOS" src="https://img.shields.io/badge/macOS-12%2B-1f425f?style=flat-square" />
  <img alt="Windows" src="https://img.shields.io/badge/Windows-10%2B-0078d4?style=flat-square" />
  <img alt="Tauri" src="https://img.shields.io/badge/Tauri-2-24c8db?style=flat-square" />
  <img alt="Rust" src="https://img.shields.io/badge/Rust-2021-ce422b?style=flat-square" />
  <img alt="Stars" src="https://img.shields.io/github/stars/appergb/openless?style=flat-square&color=805ad5" />
</p>

<p align="center">
  <strong>加入 QQ 群：1078960553</strong>
</p>

<p align="center">
  <strong>贊助商</strong>
</p>

<p align="center">
  <a href="https://www.knin.net" target="_blank" rel="noopener">
    <img alt="悠霧雲資料" src="https://www.knin.net/upload/logo.png" height="48" />
  </a>
  &nbsp;&nbsp;
  <a href="https://jiangmuran.com/" target="_blank" rel="noopener">
    <img alt="jiangmuran" src="assets/people/jiangmuran.png" width="48" height="48" />
  </a>
  <br/>
  <a href="https://www.knin.net" target="_blank" rel="noopener">悠霧雲資料 — www.knin.net</a>
  &nbsp;·&nbsp;
  <a href="https://jiangmuran.com/" target="_blank" rel="noopener">jiangmuran — jiangmuran.com</a>
</p>

<p align="center">
  <strong>開發者</strong>
</p>

<p align="center">
  <a href="https://tripmc.top/" target="_blank" rel="noopener">
    <img alt="TRIP" src="assets/people/tripmc.png" width="80" height="80" />
  </a>
  &nbsp;&nbsp;
  <a href="https://chris233.qzz.io" target="_blank" rel="noopener">
    <img alt="Chris233" src="assets/people/Chris233.png" width="80" height="80" />
  </a>
  &nbsp;&nbsp;
  <a href="https://github.com/Cooper-X-Oak" target="_blank" rel="noopener">
    <img alt="Cooper" src="assets/people/cooper.png" width="80" height="80" />
  </a>
  <br/>
  <a href="https://tripmc.top/" target="_blank" rel="noopener">TRIP — tripmc.top</a>
  &nbsp;·&nbsp;
  <a href="https://chris233.qzz.io" target="_blank" rel="noopener">Chris233 — chris233.qzz.io</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/Cooper-X-Oak" target="_blank" rel="noopener">Cooper — github.com/Cooper-X-Oak</a>
</p>

---

OpenLess 是一個跨平臺（macOS & Windows）語音輸入應用，對標 [Typeless](https://www.typeless.com/)、[Wispr Flow](https://wisprflow.ai)、[Lazy](https://heylazy.com)、Superwhisper 等商業語音輸入工具的 **完全開源** 替代品。官方網站：[openless.top](https://openless.top)。

把游標放在 ChatGPT、Claude、Cursor、Notion、郵件、聊天框任意輸入框裡，按一次全域性快捷鍵說話——OpenLess 會錄音、轉寫、按你選的模式潤色，把結果直接插入游標位置。插入失敗時會自動複製到剪貼簿，儘量保證「你說過的話不丟」。

不像那些只把語音轉成「逐字稿」的輸入法，OpenLess 的核心模式是 **AI prompt 模式**：你只管亂講，它自動補上結構、列出約束、整理出有上下文的 prompt，複製貼上就能直接餵給 ChatGPT / Claude / Cursor。

## 這個 fork 的目前重點

這個 fork 會優先把產品主路徑做紮實：**按下快捷鍵開始說話，鬆開後快速轉寫、整理，再把文字穩定插入當前游標位置**。是否接近 Typeless 這類產品，不看功能頁數，而看這條路徑是否足夠穩、足夠快、足夠像真正可每天使用的語音輸入工具。

目前維護策略如下：

- **核心目標優先**：先把「熱鍵 → 錄音 → ASR → 潤色 → 插入 / 回退」這條主鏈路做好，再談周邊功能擴充。
- **繁簡中文同等重要**：簡體中文與繁體中文都視為一級介面，不把繁中只當附帶翻譯版本。
- **Windows 11 為主要驗證平臺**：目前維護者的真機環境以 Windows 11 為主，因此 Windows 相關體驗、穩定性與回歸測試優先。
- **macOS 保持相容，但不假設已實測**：沒有 macOS 真機時，相關調整以靜態審查、文件對照與外部回報為主，不把未驗證結果寫成已確認行為。

## 一個具體的例子

按住快捷鍵，對著 OpenLess 說：

> 嗯…就是…我想讓那個 ChatGPT 幫我寫個 SQL，從 orders 表裡查上個月的訂單，按客戶分組，金額倒序，要前十個吧

鬆開快捷鍵，一秒後你的輸入框裡出現的是：

```text
請幫我寫一段 SQL，要求如下：

- 從 `orders` 表查詢上個月的訂單。
- 按客戶分組。
- 按金額倒序排序。
- 只返回前 10 條。
```

不需要修改，直接 Enter 就能問 GPT。這就是 OpenLess 想做的事：**讓你用嘴寫 prompt，比用鍵盤還快還清楚。**

## 為什麼開源 OpenLess

類似工具大多是商業 SaaS：每月訂閱、不能自帶模型、轉寫音訊會上傳到廠商伺服器、詞典和習慣沉澱在對方賬戶裡。

OpenLess 想做的是同一類體驗，但是：

- **完全開源、本地優先**。程式碼在倉庫裡，所有資料寫在你的機器上。
- **自帶雲憑據**。火山引擎 ASR + Ark / DeepSeek 相容 chat-completions，不強綁某家。
- **專門為 AI prompt 最佳化**。「清晰結構」模式會把零散口語補成有上下文、有約束、有要求的 prompt，複製貼上就能直接餵給 ChatGPT / Claude / Cursor。
- **不會替你回答**。模型只整理你的話，不會把「我們這個應用還有哪些功能沒做？」變成一份功能清單——只會補成一句通順的問題，讓你拿去問真正的 AI。

## 適用場景

- 給 ChatGPT / Claude / Cursor / Gemini 寫 prompt：口述一段需求，OpenLess 自動整理成結構化、有細節的 prompt。
- 寫郵件、寫需求文件、寫微信/Slack 長訊息：去口癖、補標點、按段落整理。
- 寫程式碼註釋、commit message、PR 描述：把腦子裡的想法直接落到游標位置。
- 任何「我懶得打字，但又必須輸出書面文字」的場景。

## 專案方向

OpenLess 只做一件事：**把語音變成可用的書面文字（尤其是 AI prompt），落到當前游標位置。**

- 主路徑不做「通用問答 Agent」、不做任務執行、不做專案分析。
- 保留劃詞語音問答（QA）作為輔助場景：僅在使用者主動選取文字並觸發時啟用，不改變產品以語音輸入為核心的定位。
- 主聽寫路徑支援「可調整的短時上下文視窗」用於潤色連貫性；不做長鏈任務記憶或通用對話 Agent。
- 輸入語音 → 轉寫 → 整理 → 插入當前輸入框。失敗時複製到剪貼簿。
- 圍繞這條主路徑完善體驗：模式選擇、詞典、歷史、選單欄、首頁報告。

## 對標參考

| 工具 | 形態 | OpenLess 的差異 |
| --- | --- | --- |
| [Typeless](https://www.typeless.com/) | 閉源 macOS / Windows / iOS，訂閱制 | 開源；專門暴露 AI prompt 模式；自帶 ASR + LLM 憑據；資料和詞典留在本機 |
| [Wispr Flow](https://wisprflow.ai) | 閉源 macOS / Windows，訂閱制 | 開源；自帶 ASR + LLM 憑據；提示詞處理原則透明可改 |
| [Lazy](https://heylazy.com) | 閉源筆記/捕獲工具 | 不做筆記容器，專做「插入到任意輸入框」 |
| [Superwhisper](https://superwhisper.com) | 閉源 macOS，訂閱制 | 開源；目前雲端 ASR 優先，本地 ASR 在 roadmap |

## 當前狀態（1.3.4-3 Beta）

- Tauri 2 + Rust 後端 + React/TS 前端；macOS 12+，Windows 10+。
- **切換式 + 按住說話** 雙模式錄音；任意階段按 `Esc` 都能取消（包括潤色 / 插入中）。
- **雲端 ASR**：火山引擎流式 ASR、OpenAI Whisper 相容批式 ASR、Apple Speech（macOS）。
- **本地 ASR**：內建 Qwen3-ASR（0.6B / 1.7B），透過 vendored `Open-Less/qwen-asr` 連結；Windows 端支援 Foundry Local Whisper。
- **潤色 Provider**：Ark / DeepSeek / OpenAI / Doubao / Anthropic 相容的 Chat Completions，以及任意 OpenAI 相容的自定義 endpoint。
- 4 種輸出模式：原文、輕度潤色、清晰結構（**AI prompt 模式**）、正式表達。另含**翻譯熱鍵**——按下後說一段話直接轉成目標語言插入（[#43](../../issues/43)）。
- **劃詞語音問答（QA）面板** — 獨立熱鍵開啟浮窗，對當前選中文字發起語音 Q&A（[#118](../../issues/118)）。
- 主視窗按「概覽 / 歷史 / 詞典 / 風格 / 設定」組織；托盤圖示常駐；浮動狀態膠囊。
- **多語言 UI** — 設定 → 語言 切換簡體中文 / 繁體中文 / English / 日本語 / 한국어（首啟按系統語言自動）。
- **應用內自動更新** — 設定 → 關於 → 檢查按鈕；CI 用 Tauri updater 簽名 manifest，客戶端校驗後下載安裝。
- **Beta 渠道（opt-in）** — 設定 → 關於 → 加入 Beta 渠道，會顯示最新 prerelease 的下載入口供手動安裝；Beta 包永遠不會被自動推送給正式版使用者（詳見 [貢獻流程](#貢獻流程)）。
- **分發渠道** — [Releases](../../releases) 直接下載 DMG/EXE，Homebrew Cask（`brew install --cask openless`），Windows 安裝程式。
- **單例項鎖** — 防止兩份 OpenLess 程序並存爭搶同一熱鍵邊沿。
- 詞典條目作為 Volcengine ASR `context.hotwords` 注入 + 潤色語義提示，每次會話累計命中數。
- 平臺原生全域性快捷鍵：macOS 使用 CGEventTap，Windows 使用低層鍵盤鉤子（`WH_KEYBOARD_LL`）。

對這個 fork 來說，當前最重要的驗收標準不是功能列表是否更長，而是以下幾點是否持續改善：

- Windows 11 常用場景下的語音輸入成功率。
- 中文輸出品質，尤其是繁體中文與簡體中文的自然度與一致性。
- 插入失敗時是否能穩定回退到剪貼簿，避免丟字。
- 熱鍵、IME、權限、更新流程是否足夠可預期，能支撐日常高頻使用。

## 本地模型設定與體驗建議

如果你想把 OpenLess 配成「本地 ASR + 本地大語言模型潤色」的組合，建議先把目標定義清楚：這裡追求的不是通用問答能力，而是**短句口語整理、低延遲、中文 / 中英混輸穩定度**。模型選型應優先看首字延遲、斷句自然度與指令服從性，而不是只看參數量。

- **顯示卡記憶體建議**：依目前實測，若要同時使用本地 ASR 與本地大語言模型，建議至少有 **8GB 顯示卡記憶體**。低於這個級別通常仍能跑部分模型，但較容易遇到載入慢、首字延遲高或切換場景後體感不穩定。
- **Windows 11 的本地 ASR 首選**：目前以 **Foundry Local Whisper** 為主；Windows 端暫不建議把 Qwen3-ASR 當作主力路徑。
- **本地大語言模型建議**：若你的本地推理工具提供 OpenAI 相容 endpoint，OpenLess 可直接接入該 endpoint 做潤色。以 8GB 級別顯示卡來說，建議優先選擇 **7B 到 9B 的 instruct 模型，並使用 4-bit 或同級量化**。
- **中文優先的推薦順序**：若重點是繁中、簡中與中英混輸的穩定度，優先考慮 **Qwen 系 7B 到 9B instruct 模型**。這一類模型通常比同級輕量模型更適合 OpenLess 的「口語 → 可直接送出文字」任務。
- **速度優先的推薦順序**：若你的目標是降低延遲、減少顯示卡記憶體壓力，**Gemma 4 e4b** 會是較務實的選擇；若只是先確認整條本地潤色鏈路可用，**Gemma 4 e2b** 也可以作為更保守的起點。
- **目前已做過的簡單測試**：`gemma-4-e4b`、`gemma-4-e2b`、`qwen3.5-9b`。如果你要在 8GB 顯示卡記憶體上追求更好的中文潤色品質，可優先沿著 Qwen 同量級 instruct 模型往下試；若優先考慮速度與穩定啟動，則可從 Gemma 4 e4b 這類較輕量模型開始。
- **不建議一開始就追更大的本地大語言模型**：對 OpenLess 這種即時語音輸入工具來說，過大的模型常帶來更高首字延遲，對日常體驗的傷害通常比品質提升更明顯。
- **建議的預設調校方向**：優先關閉思考模式、降低溫度、不要把上下文視窗拉得太大。OpenLess 的主任務是穩定整理文字，不是做長推理或多步任務規劃。

如果你只想先得到一組容易落地的配置，Windows 11 可以先從以下組合開始：

1. ASR：Foundry Local Whisper
2. LLM：Qwen 系 7B 到 9B instruct，或 Gemma 4 e4b
3. 量化：4-bit 優先
4. 思考模式：關閉
5. 用途：短句口語整理、Prompt 潤色、郵件 / 文件改寫

## Windows 11 核心驗收清單

若目標是做出接近 Typeless 的語音輸入體驗，這個 fork 每次調整後至少應回頭檢查以下主鏈路：

1. **熱鍵可預期觸發**
  在乾淨啟動後，快捷鍵能穩定開始與結束錄音，不因權限探測、焦點切換或背景啟動而卡死。
2. **停止錄音後能在可接受時間內出結果**
  從鬆開快捷鍵到看到轉寫 / 潤色結果，不應慢到打斷思路；慢路徑也要有明確狀態回饋。
3. **常用應用中的插入成功率夠高**
  至少應覆蓋瀏覽器文字框、ChatGPT / Claude、Cursor / VS Code、Notion、Slack / LINE、Word 等常見輸入場景。
4. **插入失敗時不丟字**
  若無法直接寫入當前游標，必須能可靠回退到剪貼簿，並讓使用者知道下一步該怎麼貼上。
5. **中文輸出可直接使用**
  繁體中文與簡體中文都應避免只停留在逐字稿層級，而要盡量做到斷句自然、口語收斂、適合直接送出。
6. **回歸時優先驗證 Windows 11 真機**
  若改動涉及熱鍵、IME、剪貼簿、權限、更新或視窗生命週期，預設先以 Windows 11 真機結果作為合併依據。

Beta 渠道的主要價值，也應優先服務於這份驗收清單：先把語音輸入主路徑打磨穩，再擴充周邊功能。

## Windows 11 建議回歸場景（最小集）

為了讓每次改動都持續朝「可日常使用的語音輸入工具」前進，建議至少固定回歸以下場景：

1. **瀏覽器文字框**（搜尋框、長文本輸入框）
  驗證熱鍵可用、錄音啟停、輸入焦點不丟失。
2. **AI 對話工具**（ChatGPT / Claude）
  驗證長句口語輸入後的潤色可直接送出，且不會誤插到錯誤區域。
3. **開發工具**（Cursor / VS Code）
  驗證英文符號混輸、程式語境詞彙、剪貼簿回退行為。
4. **知識與文書工具**（Notion / Word）
  驗證段落、標點、換行與多段文本插入穩定性。
5. **即時通訊工具**（Slack / LINE / Discord 任一）
  驗證短句高頻輸入、重複觸發熱鍵時的穩定性。

若改動涉及熱鍵、IME、插入、更新或權限，建議在 PR 說明中附上以上場景的最小回歸結果摘要。

## 每次改動後的最小驗證流程（Windows 11）

1. 啟動 App，確認主視窗與托盤行為符合預期。
2. 用預設熱鍵完成一次完整輸入流程（說話 → 轉寫/潤色 → 插入）。
3. 人為製造一次插入失敗情境，確認剪貼簿回退可用且不丟字。
4. 至少在兩種不同類型應用中完成實際輸入（例如瀏覽器 + 編輯器）。
5. 若此次改動觸及更新流程，額外檢查「設定 → 關於」中的更新與 Beta 通道行為。

現有自動化腳本可作為輔助，但不替代真機輸入體驗驗收。Windows 相關腳本可參考 `openless-all/app/scripts/` 下的 smoke 系列腳本（例如 `windows-smoke-suite.ps1`）。

## 下載與安裝（普通使用者）

到 [Releases](../../releases) 下載對應平臺的安裝包：
- **Windows**：`OpenLess_<版本>_x64-setup.exe` — 執行安裝程式
- **macOS**：`OpenLess_<版本>_aarch64.dmg`（Apple Silicon）或 `OpenLess_<版本>_x64.dmg`（Intel）— 開啟後拖入「應用程式」，**然後必須在終端跑這一行繞過 Gatekeeper 的"已損壞"提示**（當前包是 ad-hoc 簽名、未做 Apple 公證）：
  ```bash
  xattr -cr /Applications/OpenLess.app
  ```
- **macOS（Homebrew）**：
  ```bash
  brew tap appergb/openless https://github.com/appergb/openless
  brew install --cask openless
  xattr -cr /Applications/OpenLess.app

  # 升級到最新版本
  brew update && brew upgrade openless
  ```

首次啟動需要授予許可權：

**macOS：**
1. 授予麥克風許可權。
2. 授予輔助功能許可權。
3. **退出 OpenLess 並重新開啟**（輔助功能授權需要重啟才對全域性快捷鍵生效）。
4. 開啟「設定」，填入火山引擎 ASR 和 Ark 憑據。

**Windows：**
1. 按提示授予麥克風許可權。
2. 開啟「設定 → 許可權」確認全域性快捷鍵監聽器已啟動。
3. 在「設定」中填入火山引擎 ASR 和 Ark 憑據。

不會配火山 ASR 的話，直接看這篇圖文引導：
[OpenLess 火山 ASR 配置](docs/volcengine-setup.md)

完整使用步驟見 [USAGE.md](USAGE.md)。

## 從原始碼構建（開發者）

當前活躍程式碼庫在 `openless-all/app/`（Tauri 2 + Rust + React/TS）。macOS 構建會連結一份 vendored 的本地 ASR 引擎（[`Open-Less/qwen-asr`](https://github.com/Open-Less/qwen-asr)，fork 自 `antirez/qwen-asr`），以 git submodule 形式掛在 `src-tauri/vendor/qwen-asr/`，首次 clone 後必須先拉子模組。

```bash
# 首次 clone 後拉取子模組
git submodule update --init --recursive

cd "openless-all/app"
npm ci

# 開發模式：Vite at :1420 + Tauri shell
npm run tauri dev

# macOS release 構建（簽名、安裝、重置 TCC）
./scripts/build-mac.sh
INSTALL=0 ./scripts/build-mac.sh   # 只構建，不安裝

# Rust 型別檢查（不做完整編譯）
cargo check --manifest-path src-tauri/Cargo.toml

# 前端 TS 檢查
npm run build
```

日誌路徑：`~/Library/Logs/OpenLess/openless.log`（macOS）/ `%LOCALAPPDATA%\OpenLess\Logs\openless.log`（Windows）。

**Windows 構建** — MSVC 和 GNU/MinGW 兩種路線詳見 [`openless-all/README.md`](openless-all/README.md)。

## 貢獻流程

OpenLess 採用 **Beta / 正式版** 雙渠道分支模型。

- **`beta`** —— **Beta 渠道（開發版）**。預設分支，也是日常整合緩衝區；所有進行中的開發都先落到這裡。Beta 渠道可以直接出包，但**不會推送給普通使用者**——只有主動切換到 Beta 渠道的使用者才會拿到 Beta 包。
- **`main`** —— **正式版渠道（Stable）**。始終保持可釋出狀態，普通使用者預設拿到的就是這條線上的版本。

```text
你的 fork / topic 分支
        │  （先在目標平臺本地自測透過）
        ▼
   PR → beta   ← AI Review（一次性，僅供參考）
        │     ← 維護者輕量過一眼（範圍、跨模組影響）
        ▼
       合入 beta
        │  （定期或里程碑節點，跑雙端冒煙測試）
        ▼
       合入 main  →  打 tag `v<版本>-tauri`  →  Release CI → 推給正式版使用者
```

核心規則：

- **PR 一律打到 `beta`，不要直接打到 `main`。** GitHub 上新建 PR 的 base 已預設是 `beta`。
- **開 PR 前先在目標平臺跑通功能** —— build 綠是底線，必須做人工驗證。
- **此 fork 預設以 Windows 11 真機驗證為主。** 如果改動主要影響 Windows 熱鍵、IME、插入、更新或權限路徑，合併前應優先提供 Windows 11 本機驗證結果。
- **涉及 macOS 專屬行為時，不把未驗證結果寫成已確認。** 若沒有 macOS 真機證據，請在 PR 或文件中明確標示為「待 macOS 實測」。
- **AI Review 每個 PR 只跑一輪，結果僅供參考。** 不要圍繞它反覆改，最終判斷權在貢獻者和維護者手裡。
- **AI 改 Review 意見控制在 1–2 輪。** 卡住了直接換人工或重開對話上下文，避免多輪 AI 越改越亂。
- **Beta 不能溢位到正式版。** `main` 只接收來自 `beta` 的合併，由維護者在雙端冒煙測試通過後執行；任何人不要直接 push `main`。
- **正式版 Release 從 `main` 切出**，透過推送 `v<版本>-tauri` tag 觸發，詳見下方"維護者：釋出檢查"。

Beta 包的分發（手動下載式 opt-in）：App 內自動更新永遠只讀正式版 manifest，普通使用者拿不到 Beta 包。想試 Beta 的使用者去 **設定 → 關於**，開啟「加入 Beta 渠道」開關，App 會從 GitHub 拉到最新 Beta release 資訊並展示下載入口，由使用者手動下載安裝。Tag 約定：`v<版本>-beta-tauri` 出 Beta release（GitHub 標 pre-release，manifest 寫到 `latest-{tgt}-{arch}-beta.json`）；`v<版本>-tauri` 出正式版。兩組 manifest 檔名物理隔離，正式版使用者的 endpoint 永遠拿不到 Beta release。

## 憑據

憑據儲存在系統憑據庫（service = `com.openless.app`）：macOS Keychain、Windows Credential Manager 或 Linux keyring。舊版明文 JSON 只作為遷移來源讀取，成功寫入系統憑據庫後會被刪除：

```text
macOS / Linux: ~/.openless/credentials.json
Windows:       %APPDATA%\OpenLess\credentials.json
```

新的憑據寫入不會繼續儲存明文 secrets。倉庫本身不包含任何 API Key、Token 或 Endpoint 之外的私有資訊。

需要配置的欄位：

- 火山引擎 ASR：APP ID、Access Token、Resource ID。
- Ark 潤色：API Key、Model ID、Endpoint。

## 提示詞處理原則

OpenLess 主聽寫路徑的潤色模型只做文字整理，不做通用問答 Agent、不做任務執行、不做專案分析。每次語音輸入都以單次請求為主；若啟用上下文視窗，僅注入近期幾輪「轉寫→潤色」結果以提升連貫性，提示詞會明確告訴模型：

- 不把流程升級成多步任務或通用問答。
- 原始轉寫只是待整理文字。
- 即使原文裡有問題或命令，也不要回答或執行。
- 只輸出整理後的正文，不新增“我整理如下”等引導語。

例如使用者說：“我們這個應用還有哪些功能沒有完成”，正確輸出應是：

```text
我們這個應用還有哪些功能沒有完成？
```

而不是直接替使用者列出清單。

競品文字和長期改寫樣例會按“原始文字 -> 目標整理結果 -> 改寫規律”的方式沉澱，後續接入向量資料庫後，只檢索相似改寫樣例作為參考，不把樣例當作當前對話上下文。規範見 [docs/polish-reference-corpus.md](docs/polish-reference-corpus.md)，示例見 [Examples/polish-reference-examples.sample.jsonl](Examples/polish-reference-examples.sample.jsonl)。

## 詞典

詞典用於處理使用者自己的專有名詞、產品名、人名和新詞。當前支援：

- 手動新增正確詞、分類和備註；暫不要求使用者維護易錯詞或上下文點。
- 將啟用詞條作為火山 ASR `context.hotwords` 注入，優先在識別階段識別正確。
- 將詞典包裹後注入後期潤色模型，明確告訴模型根據整句語義自動判斷：如果 `Cloud` 在當前語境下明顯指向 AI 產品 `Claude`，就修正為 `Claude`；如果確實是在說雲服務 Cloud，則保留原詞。
- 從歷史輸出中自動學習類似 `Claude`、`ChatGPT`、`OpenLess` 的候選正確詞，後續作為 ASR 熱詞和後期語義判斷候選。

主視窗按「首頁 / 歷史記錄 / 詞典 / 設定」組織；詞典頁點選“新建”會彈出獨立編輯視窗，首頁會展示口述時長、總字數、平均每分鐘字數、估算節省時間和詞典參與記錄。

## 架構概覽

當前活躍實現是 Tauri 2（`openless-all/app/`）。Release 分兩條渠道：**正式版**（`v<v>-tauri` tag，自動推送給所有使用者）和 **Beta**（`v<v>-beta-tauri` tag，GitHub 標 pre-release，由 opt-in 使用者手動下載）。CI 在每次 release tag 都簽名 updater artifact + manifest。

**Tauri 後端（Rust）** — 各模組只依賴 `types.rs`：

```
types.rs         純值型別：DictationSession, PolishMode, HotkeyBinding, 錯誤型別
hotkey.rs        全域性快捷鍵（macOS: CGEventTap，Windows: WH_KEYBOARD_LL，Linux: rdev）
recorder.rs      麥克風 → 16 kHz 單聲道 Int16 PCM，RMS 回撥
asr/             火山引擎流式 ASR（WebSocket）+ Whisper HTTP
polish.rs        OpenAI 相容 chat-completions（Ark / DeepSeek 等）
insertion.rs     AX focused-element → 剪貼簿 + Cmd+V → 僅複製兜底
persistence.rs   歷史記錄 / 偏好設定 / 詞典 JSON + 系統憑據庫
permissions.rs   TCC 許可權檢查（輔助功能 / 麥克風）
coordinator.rs   狀態機：Idle → Starting → Listening → Processing
commands.rs      Tauri IPC 介面
```

**React 前端（`src/`）** — 狀態透過 Recoil atoms（`pages/_atoms.tsx`）管理；快捷鍵能力和繫結透過 `HotkeySettingsContext` 獲取；所有後端呼叫走 `lib/ipc.ts`。

錄音 → 轉寫 → 潤色 → 插入流水線：`快捷鍵觸發 → Recorder.start + ASR.openSession → [音訊幀] → 再次觸發 → Recorder.stop + ASR.sendLastFrame → Polish → Insert → History.save`。

詳細的不變數和模組接線規則見 [CLAUDE.md](CLAUDE.md)。

## 規劃中

進行中 / 尚未完整釋出的功能：

- 跨會話風格記憶：polish 逐漸學習使用者的語氣習慣（[#46](../../issues/46)）。
- 常用片段 Snippets：尚無 UI 和觸發邏輯。
- 歷史增強：複製按鈕、搜尋、重新潤色、重新插入。
- 貼上上一條結果快捷鍵。
- 多屏定位：膠囊跟隨焦點所在螢幕顯示。

## 維護者：釋出檢查

OpenLess 走兩條 release 渠道，分支名 = 渠道名（詳見 [貢獻流程](#貢獻流程)）。

### 通用準備（兩條渠道都要做）

- 同步更新**全部 5 處**版本號：`package.json`、`package-lock.json`（root + `packages.""` 巢狀項）、`src-tauri/tauri.conf.json`、`src-tauri/Cargo.toml`、`Cargo.lock`（找 `name = "openless"` 的那段）。CI 的 `Verify version sync` 步驟會攔截不同步的版本號。
- 執行 `INSTALL=0 ./scripts/build-mac.sh`，確認 `.app` 可啟動。
- 在乾淨機器上跑冒煙：許可權引導、快捷鍵、錄音、ASR、潤色、插入、剪貼簿兜底。
- 確認 repo 已配置 `TAURI_SIGNING_PRIVATE_KEY`，macOS 還需 Apple 簽名/公證 secrets。

### Beta 渠道 — `v<v>-beta-tauri`

1. 透過 PR review 把改動落到 `beta` 分支。
2. **在 `beta` 上**打 tag：`git tag v<v>-beta-tauri && git push origin v<v>-beta-tauri`。
3. CI 把 GitHub Release 標為 `Pre-release`，只上傳 `latest-{tgt}-{arch}-beta.json` updater manifest；正式版使用者的 `releases/latest` 重定向不受影響。
4. 在合適的頻道（issue 帖子、QQ 群）通知 opt-in Beta 使用者：可以從 設定 → 關於 → 加入 Beta 渠道 拿到最新版本下載入口。

### 正式版渠道 — `v<v>-tauri`

1. Beta 經過足夠時間 soak（或直接做最終的雙端冒煙）後把 `beta` 合到 `main`。
2. **在 `main` 上**打 tag：`git tag v<v>-tauri && git push origin v<v>-tauri`。
3. CI 釋出常規 GitHub Release 並上傳 `latest-{tgt}-{arch}.json`（不帶 `-beta` 字尾）。所有正式版使用者透過應用內 updater 收到此版本。

### 發版後驗證（每次必跑）

走 [`CLAUDE.md` → Branch & release-channel workflow → Channel distribution](CLAUDE.md) 裡的 5 步 checklist：頁面狀態（pre-release 標記）、資產檔名按渠道正確、正式版使用者流、Beta opt-in 流、原始 endpoint 抽查。

## 致謝

OpenLess 在此真誠感謝三類群體：贊助者、開發者/貢獻者，以及 LinuxDo 社群。

感謝贊助者對專案持續推進的支援；感謝開發者和貢獻者在開發、評審與改進中的長期投入。

OpenLess 也認可並感謝 LinuxDo 社群開放、務實、對開發者友好的氛圍。OpenLess 的許多想法、討論和早期反饋，都受到了 LinuxDo 所代表的開源交流精神的啟發。

此致謝不代表官方背書或隸屬關係。

## 許可

MIT
