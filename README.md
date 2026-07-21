# Convene - Multi-Agent Debate Platform

Convene is a multi-agent debate engine powered by structured LLM agents. Using a LangGraph orchestrator, it runs real-time consensus debates across domain-specific presets (Developer, Education, Startup) with cross-examination, tool usage, consensus evaluation, and real-time SSE streaming.

## 🔗 Live Deployments & Repositories

* **Live Website (Frontend)**: [convene-six.vercel.app](https://convene-six.vercel.app)
* **Live API Server (Backend)**: [convene-backend-0fwn.onrender.com](https://convene-backend-0fwn.onrender.com)
* **Frontend Repository**: [github.com/ArulSrivastva/Convene](https://github.com/ArulSrivastva/Convene)
* **Backend Repository**: [github.com/uniquedev200/Convene-Backend](https://github.com/uniquedev200/Convene-Backend)

---

## 🚀 Key Features

* **Multi-Agent Consensus Graphs**: Runs structured debates using domain-specific personas (e.g., Architect, Security, Performance) who challenge each other to reach a final scored consensus.
* **Google OAuth Sign-In**: Integrated with Supabase Auth to support Google Sign-In and local accounts.
* **Database-Less Fallback**: Auto-detects database configuration status—falls back to memory-only execution when database pools are offline or missing credentials.
* **Responsive Mobile Layout**: Optimized with a responsive sliding sidebar drawer, overlay backdrop, and hamburger menu toggle for mobile devices.
* **Real-time Streaming**: Connects directly to FastAPI's Server-Sent Events (SSE) stream to display live debate thoughts, agent challenges, and tools in action.

---

## 🛠️ Architecture & Tech Stack

```
POST /debate  →  LangGraph Orchestrator  →  4 Domain Personas (LLM Agents)
                   ↕                              ↕
              Tool Calls (Web Search,          Cross-Examination
              URL Fetch, GitHub, Docs)         (Agent Challenges)
                   ↕                              ↕
              Scoring + Weighting  →  Consensus Finalization  →  SSE Stream
```

* **Backend**: FastAPI, LangGraph, Python 3.11+, PostgreSQL (Supabase).
* **Frontend**: Next.js 15, TailwindCSS, TypeScript, Lucide Icons, Supabase Auth.

---

## ⚙️ Quick Start

### 🐍 Backend Setup

1. **Install dependencies**:
   ```bash
   pip install -e ".[test]"
   ```
2. **Configure environment**:
   Create a `.env` file in the root directory:
   ```env
   GROQ_API_KEY=your_groq_api_key
   JWT_SECRET=your_jwt_signing_secret
   SUPABASE_URL=https://zxnfcbojuxbdqzryqtaw.supabase.co
   SUPABASE_ANON_KEY=sb_publishable_myU9f34KZ5iNyLiKet5-cQ_y0xc0_PC
   SUPABASE_DB_URL=optional_postgres_connection_string
   ```
3. **Run the server**:
   ```bash
   uvicorn app.main:app --port 8000 --reload
   ```

### ⚡ Frontend Setup

1. **Install dependencies**:
   ```bash
   cd frontend
   npm install
   ```
2. **Configure environment**:
   Create a `frontend/.env.local` file:
   ```env
   NEXT_PUBLIC_SUPABASE_URL=https://zxnfcbojuxbdqzryqtaw.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=sb_publishable_myU9f34KZ5iNyLiKet5-cQ_y0xc0_PC
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```
2. **Run the development server**:
   ```bash
   npm run dev
   ```

---

## 🧪 Testing

Run backend tests using pytest:
```bash
pytest -q                    # Run all test suites
pytest tests/test_api.py     # API integration tests
pytest tests/test_graph.py   # LangGraph orchestrator tests
```
