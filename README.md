# FinVoice 🎙️💰
> **“Just say it. FinVoice plans the rest.”**

FinVoice is a voice-first personal money management and planning application featuring a proactive **AI Planning Agent** that studies your entered financial data and spending history to optimize and adapt your monthly budget across 10 distinct categories.

---

## ✨ Key Innovations & Features

### 1. 🎙️ Floating Voice ORB & Natural Language Financial Parser
- **Voice ORB**: A prominent floating voice button with multi-stage glowing concentric waves and pulse animations:
  - **Idle**: Gentle breathing pulse glow.
  - **Listening**: Expanding multi-layer audio rings and microphone indicator.
  - **Processing**: Rotating glowing core and speech understanding state.
  - **Confirmation**: Clean "I understood" card showing parsed Type, Amount (₹), Category, Account, Date, and Transcript.
- **Ambiguity Detection**: If an amount is detected without a clear category (e.g., *"Spent 450"*), FinVoice does not guess silently—it immediately prompts the user with quick-select candidate categories to resolve clarification.
- **Natural Language Parsing**:
  - *"Spent 450 on groceries"* ➔ ₹450 under **Food & Groceries**
  - *"Paid 6000 rent"* ➔ ₹6,000 under **Housing**
  - *"Bought clothes for 1200"* ➔ ₹1,200 under **Shopping**
  - *"Paid my Netflix subscription"* ➔ ₹499 under **Subscriptions**
  - *"Received salary of 30000"* ➔ ₹30,000 under **Income**
  - *"How much can I spend this week?"* ➔ Instant Safe-to-Spend voice & visual calculation
  - *"Plan my money for this month"* ➔ Triggers the Planning Agent workflow

### 2. 🧠 Flagship Planning Agent ("Plan My Money")
- **Dynamic Personalized Allocation**: Not hardcoded—analyzes total income, fixed commitments (rent, utilities, active subscriptions, insurance premiums), spending trends, and selected financial priorities (Save money, Control expenses, Build emergency fund, Plan monthly budget).
- **Adaptive Learning**: Recognizes evolving spending patterns over time:
  - If grocery spending surges, adjusts next month's allocation with a buffer and explains why.
  - If entertainment spending decreases, reallocates surplus to the Emergency Fund and Savings.
- **Focus Modes**: Toggle between **Balanced (50/30/20)**, **Aggressive Wealth Saver**, and **Emergency Shield Priority**.
- **Actions**: `Accept Plan`, `Edit Plan`, `Regenerate Plan`.
- **Educational Language**: Responsible planning language (*"Planning suggestion"*, *"Educational insight"*) without misleading financial promises.

### 3. 📊 Main Dashboard
- Dynamic time-aware greeting (*"Good evening, [Name]"*).
- 4 Key Metric Cards:
  - **Monthly Income** (Mint)
  - **Total Spent** (Coral)
  - **Remaining Balance** (Cyan)
  - **Safe to Spend** (Gold - 7-day safe cap based on remaining days)
- **Visual Spending Ring**: Neon radial SVG ring tracking percentage of budget consumed.
- **"FinVoice says" AI Card**: Dynamic AI insight synthesized from real stored data.
- **Upcoming Bills Preview & Quick Pay**: Mark bills as paid with 1 click.
- **Recent Expenses Ledger**: Full history with voice-tagged indicators.

### 4. 🗂️ 10 Dedicated Financial Categories
1. **Housing** (Rent / Loan)
2. **Food & Groceries**
3. **Transportation**
4. **Bills & Utilities**
5. **Subscriptions**
6. **Insurance**
7. **Education**
8. **Entertainment**
9. **Shopping**
10. **Emergency Fund**

Every category card shows an icon, current spend, planned target, remaining buffer, progress bar, percentage used, and is clickable to inspect all transactions in that category.

### 5. 📑 Complete Money Hub (Transactions, Bills, Subscriptions, Insurance)
- **Transactions**: Search, filter by category, filter by type (Income vs Expense), and manual "+ Expense" entry.
- **Bills**: Track rent, electricity, WiFi, water, and phone bills with statuses (*Upcoming*, *Due soon*, *Paid*).
- **Subscriptions**: Monthly vs. yearly cost calculation and subscription load insights.
- **Insurance**: Health, Life, Vehicle, and Other policies with renewal reminders.

### 6. 🌙 Nightly Expense Reminder
- Non-intrusive banner prompting users if no expense has been recorded for the day:
  *"Looks like you haven't recorded today's expenses yet. Want to update them?"*
- Buttons: **Add Expense**, **Use Voice**, **Later** (can be toggled in Settings).

### 7. 🔐 Firebase Authentication & Security
- Integrated with Firebase Web SDK v12.19.0:
  - Email/Password Signup & Login
  - Google Sign-In Popup
  - Password Reset
- `firestore.rules` included, strictly scoping documents to `request.auth.uid`.
- Instant One-Click Demo Mode available for testing.

---

## 🚀 Running the Application Locally

The application comes with a zero-dependency HTTP server:

```bash
# Start server
node server.js
# Or via npm
npm start
```

Visit **`http://localhost:3000`** in your browser.

---

## 📁 Project Structure

```text
Finvoice/
├── index.html              # Core single-page application structure & modals
├── server.js               # Zero-dependency local dev server with ESM MIME support
├── package.json            # Project manifest
├── firestore.rules         # Security rules securing collections to user UID
├── css/
│   └── styles.css          # Dark-first glassmorphism design system & animations
└── js/
    ├── app.js              # Application entry point and orchestrator
    ├── ui.js               # View router, screen rendering, modals, and drawers
    ├── state.js            # Central reactive store, metrics, and persistence
    ├── voice-agent.js      # Natural language parser, Web Speech API & Voice ORB
    ├── planning-agent.js   # Dynamic financial allocation and adaptive engine
    ├── demo-data.js        # Realistic ₹30,000 starter portfolio data
    └── firebase-config.js  # Firebase v12.19.0 configuration & service bridge
```
