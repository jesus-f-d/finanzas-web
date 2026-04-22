# Finanzas Web

A family financial management application built with pure HTML — no frameworks, no dependencies, no server required. Simply download the file and open it in your browser.

## ✨ Features

- **Dashboard** — General balance summary, weekly income and expenses, and progress bars by category (Expenses, Loans, Credits, Kash)
- **Register** — Record transactions as Income, Personal Expense, Bank Credit, or Kash; also supports transfers between accounts (Cash / Banking)
- **Movements** — Filterable transaction history by type and week
- **Stores** — Track expenses by store or merchant
- **Loans** — Record and manage loans with payment schedules
- **Reports** — Weekly/monthly/yearly views with income breakdown, business expenses, household expenses, and summary totals

## 🚀 Quick Start

1. Download the `Finanzas.html` file
2. Open it in any modern browser
3. Start recording your transactions

Data is automatically saved to your browser's `localStorage`. Nothing is sent to any server.

## 🔧 Connecting to a Database

Currently, the application uses `localStorage` for data persistence. To connect it to a real database, replace the following functions in the script:

| Current Function | Purpose | Replacement |
|---|---|---|
| `loadMovs()` | Loads transactions from localStorage | Fetch to your API GET /movements |
| `saveMovs()` | Saves transactions to localStorage | Fetch to your API POST /movements |
| `loadTraspasos()` | Loads transfers | Fetch to your API GET /transfers |
| `saveTraspasos()` | Saves transfers | Fetch to your API POST /transfers |
| `loadPrestamos()` | Loads loans | Fetch to your API GET /loans |
| `savePrestamos()` | Saves loans | Fetch to your API POST /loans |

Example of how `loadMovs()` would look with a REST API:

```javascript
async function loadMovs() {
  const res = await fetch('https://your-api.com/movements');
  movs = await res.json();
}
```

## 🛠️ Technology Stack

- HTML5 + CSS3 + JavaScript vanilla
- Fonts: [Sora](https://fonts.google.com/specimen/Sora) + [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (Google Fonts)
- Persistence: `localStorage` (no database by default)

## 📄 License

MIT — Use, modify, and share freely.
