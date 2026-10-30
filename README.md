<div align="center">

# TRADELOG
### A private trading journal. Built for discipline.

**Trade. Review. Improve.**

A lightweight, no-subscription journal for tracking your Groww trades, understanding your P&L, and keeping your decisions accountable.

<br/>

![Status](https://img.shields.io/badge/status-personal%20project-27c995?style=flat-square)
![Hosting](https://img.shields.io/badge/hosting-GitHub%20Pages-111827?style=flat-square&logo=github)
![Storage](https://img.shields.io/badge/storage-browser%20IndexedDB-2563eb?style=flat-square)
![Cost](https://img.shields.io/badge/cost-₹0-16a34a?style=flat-square)

</div>

---

## The idea

Trading platforms show you orders and positions. TradeLog gives you a simple place to look back at the decisions behind them.

No crowded terminal. No complicated setup. No subscription.

At the end of a trading session, export your Groww tradebook, import it here, and let the journal organise the activity into a readable performance history.

## What it does

| | Feature | What it gives you |
|:--:|---|---|
| ↗ | **Groww CSV import** | Bring in executed trades from a downloaded tradebook |
| ◷ | **Daily trade history** | Review activity by date and instrument |
| ₹ | **P&L overview** | See recorded gross P&L, capital activity and averages |
| ◎ | **Win / loss signal** | A simple read of the journal's recorded results |
| ↻ | **Duplicate protection** | Avoid importing the same matching trade group twice |
| ⇩ | **CSV backup & restore** | Keep a portable copy of your journal |

## The daily ritual

```text
Trade on Groww
     ↓
Download the executed-trades CSV
     ↓
Open TradeLog
     ↓
Import Groww tradebook
     ↓
Review the numbers. Learn from the session.
```

A few minutes at the end of the day can make your trading decisions easier to review over time.

## Built to stay simple

- **Frontend:** HTML, CSS and vanilla JavaScript
- **Hosting:** GitHub Pages
- **Local database:** IndexedDB
- **Import / export:** CSV
- **Backend:** None
- **Paid API:** None

TradeLog is a static website. Your records are saved in the browser you use to access it; they are not uploaded to GitHub.

## Get your own copy

1. Download or clone this repository.
2. Create a GitHub repository for your journal.
3. Add `index.html` to the repository root.
4. Open **Settings → Pages**.
5. Under **Build and deployment**, select **Deploy from a branch**.
6. Choose `main` and `/(root)`, then save.
7. Open the GitHub Pages address shown by GitHub.

That's it. No build step, package manager, server, or environment variables.

## Your EOD import

1. Sign in to Groww and download the **executed trades / tradebook CSV** after the session.
2. Open your TradeLog website.
3. Choose **Import Groww tradebook** and select the file.
4. Review the import summary and confirm.
5. Check the updated history and performance snapshot.

The first importer expects execution-level rows with a trade date, symbol, buy/sell side, quantity and price. It is not designed for an order list or a daily summary export.

## A note on the numbers

Accuracy matters more than a pretty green number.

- Matched buy and sell executions are paired using **FIFO** to estimate gross realised P&L.
- Brokerage, STT, GST, exchange charges and other fees are **not deducted** by this first version. The result can differ from Groww's final net P&L.
- “Capital used” is the buy-side turnover for an instrument/date group. It is an activity measure, not necessarily the margin blocked by the broker.
- Unmatched open quantities are not marked to market. Groups with no matched opposite-side quantity are skipped.
- Groww report headers can vary. If the importer cannot recognise a file, verify that it is the tradebook and adapt the column mapping to that export.

**Treat the dashboard as a personal review journal, not a broker statement, tax report, or investment recommendation.**

## Keep your journal safe

Your trading history is stored locally in your browser using IndexedDB. It is not automatically synced between devices and GitHub Pages does not hold a copy of it.

- Export a TradeLog backup regularly.
- Keep the backup somewhere separate from your computer.
- Use **Restore backup** to add records back into the journal.
- Avoid private/incognito windows.
- Be careful when clearing browser data or resetting/changing devices; local records may become unavailable.

Records are not automatically deleted after one year, but no browser-only storage should be treated as your only backup.

---

<div align="center">

**Built for one trader: to trade with more awareness, not more noise.**

*TradeLog · Personal project · ₹0 API cost*

</div>
