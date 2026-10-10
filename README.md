# Lukas AI Personal Assistant — Desktop Personal AI Agent

> **Positioning:** A personal AI assistant that remembers you, keeps you in mind, and gets things done for you.  
> The core is **Living Memory** + **Proactive Assistance** + **Task Execution**.

| Module | Implementation Status |
| --- | --- |
| Desktop Shell | Electron 30 + Next.js 14 App Router; single-instance lock, system tray, native notifications, and launch at startup |
| Single Long-Running Conversation | SSE streaming responses; messages are **persisted** locally, so they are not lost after refreshes or restarts |
| Main Dashboard | Greeting based on time of day, quick-intent chips, morning/evening briefings, body signals, active tasks, scheduled tasks, and recently completed tasks |
| Task Execution | A **server-side task engine** genuinely drives task progress based on time calculations; execution logs, called tools, pause/resume/retry/cancel controls, and Markdown deliverables |
| Memory Management | Create, read, update, and delete Living Memory; filter by type; semantic/text retrieval; **automatic extraction** with batch confirmation/ignore for pending memories |
| Connectors | Real Google/Microsoft OAuth (authorization code flow + AES-256-GCM encrypted tokens + automatic refresh); real-time retrieval and synchronization of email and calendar summaries |
| Community Skills Spark | Skill marketplace: install, uninstall, and run skills; running a skill converts it into a background task |
| Scheduled Tasks | Five-field cron scheduler that automatically creates background tasks and sends notifications when scheduled times arrive |
| Proactivity | Automatic generation of morning/evening briefings, task-completion notifications, and scheduled-task trigger notifications |
| Notification Center | Unread badge, mark all as read, delete individual notifications, and click to navigate to the corresponding task |
| Global Search | Unified search and navigation across memories, tasks, conversations, and skills |
| Settings & Permissions Center | Preferred form of address, assistant name, avatar, tone, proactivity level, areas of interest, permission toggles, local-first mode, and data export |
| LLM Configuration | Select the provider directly in Settings (OpenAI / Claude / Qwen / DeepSeek / Custom), along with the model and API key; changes take effect in real time |
| Community Skills Spark | Skill marketplace: install, uninstall, and run skills; 16 skills are preinstalled by default: `wecom`, `speedsheet`, `slides`, `skill-installer`, `skill-creator`, `product-knowledge-self`, `pdf`, `microsoft`, `linear`, `health-facts`, `github`, `email-workflow-discovery`, `email-connector-initialization`, `doc`, `dingtalk`, and `google` |
| Automatic Skill Invocation | Automatically invokes installed skills based on user intent during conversations, generates structured documents, and archives them as deliverables |
| Onboarding | First-launch setup flow covering preferred form of address, assistant naming, avatar, areas of interest, and tone |
| Persistence | PostgreSQL + pgvector (optional), or in-memory storage; other entities are stored as local JSON files (see the data directory below) |
| LLM | OpenAI / Claude / Qwen / DeepSeek / custom OpenAI-compatible gateway; automatically falls back to local responses when no API key is configured or when a real API call fails |
| Voice & Attachments | Voice input via Web Speech / CPI audio bridge, plus text attachments used as context |
