# Autonomous AI-Powered LinkedIn Content Agent (n8n Workflow)

An automated content generation and publishing pipeline built using **n8n**, integrating web research intelligence, large language models (LLMs), and a Telegram human-in-the-loop review mechanism.

##  Project Overview
This workflow automates the entire lifecycle of creating professional LinkedIn content:
1. **Triggers** on-demand via a Telegram message.
2. **Researches** real-time data and articles using the **Tavily API**.
3. **Generates** an optimized LinkedIn post draft using **Google Gemini**.
4. **Reviews** the content securely via **Telegram** interactive buttons (Approve/Reject).
5. **Publishes** directly to **LinkedIn** upon approval.

##  Workflow Architecture & Nodes
* **Telegram Trigger:** Listens for user prompt requests to start the generation sequence.
* **HTTP Request (Tavily API):** Performs automated web searches to gather fresh context.
* **AI Agent (Google Gemini Chat Model + Memory):** Structures and formats the gathered information into an engaging post.
* **Send a Text Message & Telegram Trigger1:** Sends the drafted post to Telegram for human review and captures the callback response (`Approve`/`Reject`).
* **Switch:** Evaluates the user's decision.
* **LinkedIn (Create a post):** Automatically publishes the approved content.

##  Tech Stack
* **n8n** (Workflow Orchestration)
* **Google Gemini LLM** (Content Generation)
* **Tavily API** (Web Search & Research)
* **Telegram Bot API** (Triggers & Human-in-the-Loop Approval)
* **LinkedIn API** (Publishing)
* **Webhooks**
