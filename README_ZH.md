# Awesome Agent Skills

<p align="center">
  <img src="assets/logo.png" alt="Awesome Agent Skills" width="700" />
</p>

<p align="center">
  <a href="https://awesome.re">
    <img src="https://awesome.re/badge.svg" alt="Awesome" />
  </a>
  <a href="CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" alt="歡迎 PR" />
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square" alt="授權：MIT" />
  </a>
</p>

<p align="center">
  <a href="README.md">English</a> | <a href="README_ZH.md">繁體中文</a>
</p>

一份精選的連結目錄，收錄由外部來源維護的 Agent Skills、Skill 集合，以及支援 AI Agent 工作流程的工具。

> [!IMPORTANT]
> 本專案只做連結型目錄。Skill 內容應留在來源儲存庫；一般收錄 PR 請勿在本儲存庫加入 `SKILL.md`、腳本、複製的 Skill 目錄或平台專屬索引。

## 收錄範圍

本目錄收錄：

- **Agent Skills** — 有公開實作、可直接使用且可重複運用的指令套件。
- **Skill Collections** — 包含多個可用 Agent Skills 的儲存庫。
- **Tooling & Integrations** — 為 Agent 工作流程設計的外掛、CLI、MCP 整合及相關專案。

本儲存庫不是套件註冊中心、不代管社群 Skill 檔案，也不代表已對連結專案完成安全審查或背書。每個項目仍由其上游擁有者維護並授權。

## 瀏覽目錄

### Agent Skills

#### 開發與程式工具

- [UIZZE anti-ui-slop](https://github.com/uizze/uizze/tree/main/skills/anti-ui-slop) — 根據真實介面參考建立產品專屬 UI 設計契約，並執行發布前完成度檢查。 `Type: Skill` · `Platforms: Cross-platform`

#### 數據與分析

- [credit-risk-model](https://github.com/W-Y-P/credit-risk-model) — 引導信用風險模型開發、驗證、報告與策略分析。 `Type: Skill` · `Platforms: Cross-platform`
- [Xquik x-twitter-scraper](https://github.com/Xquik-dev/x-twitter-scraper) — 透過 REST、MCP、SDK 或 webhook 工作流程處理 X 研究、資料擷取、監測與需確認的發布操作。 `Type: Skill` · `Platforms: Cross-platform`

#### 溝通與寫作

- [essay-writer](https://github.com/shimellism-eng/essay-writer-editor/tree/main/skills/essay-writer) — 規劃、起草、研究、編修與審閱文章，同時保留作者語氣、證據與不確定性。 `Type: Skill` · `Platforms: Codex, Agent Skills-compatible agents`

#### 創意與媒體

- [runapi-cli-skill](https://github.com/runapi-ai/cli-skill) — 教導 Agent 透過 RunAPI CLI 執行影像、影片、音訊與語言模型工作。 `Type: Skill` · `Platforms: Cross-platform`

#### 生產力與組織

- [wiki](https://github.com/plasma-ai/wiki/tree/main/wiki/skills/wiki) — 透過具確定性行為的 CLI，建立並查詢已索引的 Markdown 知識庫。 `Type: Skill` · `Platforms: Codex, Claude Code`

### Skill Collections

- [Suede Creator Skills](https://github.com/JasonColapietro/suede-creator-skills) — 涵蓋 Agent 編排、程式碼審查、評估、產品、設計與成長工作流程的多領域集合。 `Type: Collection` · `Platforms: Cross-platform`

### Tooling & Integrations

- [Agent QA](https://github.com/vostride/agent-qa) — 透過 CLI、MCP 伺服器與三個以證據為導向的 Agent Skills，執行自然語言網頁與行動應用程式 QA 工作流程。 `Type: CLI + MCP + Collection` · `Platforms: Codex, Agent Skills-compatible agents`
- [TweetClaw](https://github.com/Xquik-dev/tweetclaw) — 提供受控的 X 研究、發布、媒體、追蹤者匯出、抽獎與監測工作流程。 `Type: Plugin + Skill` · `Platforms: OpenClaw, Agent Skills-compatible agents`

## 使用收錄專案

1. 開啟條目所連結的正式來源，閱讀最新文件。
2. 使用前先檢查其 `SKILL.md`、腳本、相依套件、所需權限與外部服務。
3. 依上游文件為你的 Agent 平台完成安裝。
4. 確認授權、平台支援、資料處理方式與安全假設符合你的環境。

相容性與可用性可能改變，請以上游儲存庫為準。

## 參與貢獻

一般收錄 PR 請遵循以下規則：

1. 在適合的分類新增或更新一個上游專案。
2. **同時**修改 `README.md` 與 `README_ZH.md`，並同步名稱、網址、類型及平台資訊。
3. 僅修改這兩個檔案；請勿把上游 Skill 複製到本儲存庫。

條目格式：

```markdown
- [專案名稱](正式公開來源) — 一句精簡、客觀的說明。 `Type: Skill` · `Platforms: Cross-platform`
```

完整的收錄資格、排序、揭露、PR 範圍與 commit 簽署規則，請見 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 參考資料

- [Agent Skills 規格](https://agentskills.io/)
- [使用 Codex 建立 Skills](https://learn.chatgpt.com/docs/build-skills)
- [使用 Skills 擴充 Claude](https://code.claude.com/docs/en/skills)

## 授權與免責聲明

本儲存庫的文件與素材採用 [MIT License](LICENSE)。連結專案各自適用其授權與條款；獲得收錄不代表本專案背書、保證相容性或已完成安全審查。
