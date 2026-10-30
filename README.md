# TradeLog — GitHub Pages

A free, static trading journal. It uses HTML, CSS, JavaScript and IndexedDB in your browser.

## Publish on GitHub Pages
1. Create a GitHub repository (for example, `tradelog`).
2. Upload `index.html` to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch **main** and folder **/(root)**, then Save.
6. Open the published GitHub Pages URL after deployment finishes.

## Daily Groww workflow
1. After market hours, download your **executed trades / tradebook CSV** from Groww.
2. Open TradeLog and choose **Import Groww tradebook**.
3. Select the CSV. The importer looks for trade date, symbol, buy/sell side, quantity and price columns.
4. It groups executions by date and instrument, matches buys and sells using FIFO, and calculates gross realised P&L for matched quantities.
5. Re-importing the same file skips matching imported groups.

### Important calculation limitations
- This first importer is designed for an execution-level tradebook CSV, not an order book or a daily summary report.
- P&L is calculated from matched buy/sell executions before brokerage, taxes and other charges. It may differ from Groww's final net P&L.
- Capital used is the buy-side turnover for each date/instrument group. For short-first intraday trades, this is a simple activity measure, not margin actually blocked.
- Trades with no matched opposite-side quantity (for example, open positions) are skipped. Partial matched quantities are calculated; unmatched quantity is not valued.
- Groww's exact CSV column names can vary by report/export. If the importer says it cannot identify columns, share a sample CSV (remove personal details first) and the header mapping can be tailored.

## Data storage and backups
- Trades are stored in the browser's IndexedDB and are not automatically deleted after one year.
- Data is local to the browser and device; GitHub Pages does not store your trade records or sync them across devices.
- Export a TradeLog backup regularly and store it somewhere safe.
- Use **Restore backup** to add records from a previously exported TradeLog CSV.
- Clearing browser site data, using private browsing, or changing browser/device can make local records unavailable. Back up regularly.
