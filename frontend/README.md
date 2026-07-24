# Convene - Debate Web Console

This is the Next.js web application console for the Convene Multi-Agent Debate Platform. It connects to the FastAPI backend to configure, stream, visualise, and review multi-agent consensus debates.

## Live Deployments & Repositories

* **Live Website**: [convene-six.vercel.app](https://convene-six.vercel.app)
* **GitHub Repository**: [github.com/ArulSrivastva/Convene](https://github.com/ArulSrivastva/Convene)
* **Live API Backend**: [convene-backend-0fwn.onrender.com](https://convene-backend-0fwn.onrender.com)

---

## Features

* **Google OAuth Sign-In**: Integrated with Supabase Auth to authenticate sessions via Google or local email/password credentials.
* **Responsive Drawer Navigation**: Custom mobile layout featuring a sliding sidebar drawer, backdrop overlay, and Hamburger Menu toggle button.
* **Consensus Radar Visualizer**: Renders a dynamic HTML5 radar chart displaying how active agent personas align on debate choices.
* **Real-time Live Stream**: Subscribes to FastAPI Server-Sent Events (SSE) to track live agent stance changes, challenges, and tool calls.
* **Consensus Report Renderer**: Formats final consensus reports including win percentages, trade-off checklists, and suggested implementation code.
* **Settings & Customization**: Supports Light/Dark mode themes and dynamic API endpoint targeting.

---

## Getting Started

1. **Install dependencies**:
   ```bash
   npm install
   ```

2. **Configure environment variables**:
   Create a `.env.local` file in the directory:
   ```env
   NEXT_PUBLIC_SUPABASE_URL=https://zxnfcbojuxbdqzryqtaw.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=sb_publishable_myU9f34KZ5iNyLiKet5-cQ_y0xc0_PC
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```

3. **Run the development server**:
   ```bash
   npm run dev
   ```

4. **Build for production**:
   ```bash
   npm run build
   ```
