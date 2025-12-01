# **EdgeMind – AI-Powered Edge Personal Assistant**

EdgeMind is an AI-powered personal knowledge and task assistant built entirely on **Cloudflare’s edge platform**.
It combines Workers AI, Workflows, Durable Objects, and Realtime chat to deliver an intelligent assistant that can **remember**, **reason**, and **respond** instantly—without relying on traditional servers.

---

## 🚀 **What It Does**

EdgeMind lets users:

* Chat naturally with an AI assistant (powered by **Llama 3.3 on Workers AI**)
* Store personal notes, tasks, preferences, and reminders
* Recall previously stored information
* Execute multi-step reasoning through Cloudflare **Workflows**
* Interact through a **realtime web chat interface**
* Persist memory/state through **Durable Objects**

All logic runs on Cloudflare’s global edge network for low latency and high performance.

---

## 🧠 **Core Architecture**

### **1. Workers AI (LLM)**

Used for:

* Natural language understanding
* Extracting user intent (“store this”, “recall that”, “answer this”)
* Generating responses

Model: **Llama 3.3 via Workers AI**

---

### **2. Cloudflare Workflows**

Handles multi-step execution, for example:

1. Classify user message
2. Process or store memory
3. Generate the assistant’s reply
4. Return the final output to the UI

Workflows allow the app to run structured, long-lived tasks without managing infrastructure.

---

### **3. Durable Objects (Memory / State)**

Each user/session gets a DO instance that stores:

* Notes
* Tasks
* Conversation context
* Preferences
* Saved “memories”

Provides persistent state across sessions.

---

### **4. Cloudflare Pages + Realtime**

A minimal chat UI built using Cloudflare Pages:

* Users send messages
* Realtime sync pushes bot responses instantly
* Lightweight, no heavy frontend required

---

## 📁 **Project Structure**

```
/
├── workflows/
│   └── messageFlow.js        # Main workflow logic
├── src/
│   ├── worker.js             # Worker entrypoint
│   ├── memory.js             # Durable Object for state
│   └── ai.js                 # Workers AI (LLM) handler
├── public/
│   └── index.html            # Simple Realtime chat UI
├── package.json
├── wrangler.toml
└── README.md
```

---

## 🔧 **Setup Instructions**

1. Install dependencies:

```bash
npm install
```

2. Authenticate with Cloudflare:

```bash
npx wrangler login
```

3. Run locally:

```bash
npx wrangler dev
```

4. Deploy to Cloudflare:

```bash
npx wrangler deploy
```

---

## 🎯 **Key Features to Highlight for Cloudflare Review**

* Uses **Workers AI** for LLM inference
* Uses **Workflows** for orchestration and multi-step reasoning
* Uses **Durable Objects** for memory/state
* Uses **Pages + Realtime** for chat UI
* Demonstrates a full-stack edge-native AI app

This aligns directly with the optional assignment requirements.

---

## 🗺️ **Potential Extensions (Future Work)**

* Voice input via Whisper on Workers AI
* Scheduled reminders via Cron Triggers
* Multi-user accounts with authentication
* A memory ranking system to prioritize important notes
* Integration of Python Workflows for ML-heavy tasks

---

## 📬 **Contact**

If you’re reviewing this project and want a deeper walkthrough, I’d love to discuss the architecture, decisions, or potential improvements in more detail at siamahmed@txstate.edu

---

