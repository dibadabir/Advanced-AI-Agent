# 🏋️ AI Fitness App

A personal fitness assistant built with **Streamlit**, **AstraDB**, and **Langflow** multi-agent workflows. Log your stats, set goals, generate AI-recommended macros, and ask a context-aware fitness AI anything.

> Built by following [Tech With Tim's tutorial](https://www.youtube.com/watch?v=msLovKSj8Q0) to recreate an advanced AI Agent.
>
> Original repo: [techwithtim/Advanced-Multi-Agent-Workout-App](https://github.com/techwithtim/Advanced-Multi-Agent-Workout-App)

---

## ✨ Features

- **Profile** — Track name, age, weight, height, gender & activity level
- **Goals** — Select from Muscle Gain, Fat Loss, Stay Active
- **AI Macros** — Generate personalised calorie/protein/fat/carb targets via Langflow
- **Notes** — Add and delete notes stored with vector embeddings in AstraDB
- **Ask AI** — Ask fitness questions with your full profile passed as context

---

## 🗂 Project Structure

```
├── main.py           # UI & entry point
├── ai.py             # Langflow integrations (Ask AI + Macros)
├── db.py             # AstraDB connection & collection setup
├── profiles.py       # Profile read/create
├── form_submit.py    # DB write operations
├── AskAIV2.json      # Langflow flow — Ask AI
└── Macro_Flow.json   # Langflow flow — Macro generation
```

---

## ⚙️ Setup

```bash
pip install streamlit astrapy python-dotenv langflow requests
```

Copy `sample.env` → `.env` and fill in:

```env
ASTRA_ENDPOINT=...
ASTRA_DB_APPLICATION_TOKEN=...
LANGFLOW_TOKEN=...
```

Import `AskAIV2.json` and `Macro_Flow.json` into Langflow, then update `LANGFLOW_ID` in `ai.py`.

```bash
streamlit run main.py
```

---

## 🧠 What I Learned

- **AstraDB** — Cloud NoSQL with built-in vector embeddings, requiring zero manual embedding code
- **Langflow** — Building visual AI pipelines
- **Streamlit** — Using `@st.fragment()` to prevent full-page rerenders, and `st.session_state` to keep UI in sync with database writes

---

## 🔧 How I'd Improve It

| Area | Idea |
|---|---|
| **Progress tracking** | Store historical data and visualise trends |
| **Workout plans** | Add a third Langflow agent to generate weekly training plans |

---

*All credit for the original architecture goes to [Tech With Tim](https://github.com/techwithtim).*
