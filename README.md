IMPORTANT: THIS APP WAS CREATED IN GOOGLE AI STUDIO UNDER PROMPTS BY EOZALP. IT HAS NOT BEEN TESTED IN REAL ENVIRONMENTS AND MAY CONTAIN BUGS.


# ZenLedger - Offline Accounting PWA

ZenLedger is a local-first, offline-ready, private, double-entry accounting web application. All data is stored exclusively on your device using IndexedDB, ensuring your financial information remains private and accessible even without an internet connection. It is designed as a Progressive Web App (PWA) for a mobile-first, "thumb-ready" UI/UX.

## App Link

You can access the live application here:
[eozalp.github.io/zenpwaledger/zenpwaledger](https://eozalp.github.io/zenpwaledger/zenpwaledger)

## Installation (for local development/hosting)

This project is a pre-built PWA. For local hosting or deployment, you generally only need to serve the `zenpwaledger` directory.

1.  **Clone the repository (if applicable):**
    ```bash
    git clone <your-repository-url>
    cd zenpwaledger
    ```
    (Note: If you just copied the `zenpwaledger` folder, you can skip cloning and proceed to serving.)

2.  **Serve the directory:**
    You can use any static file server. For example, using Node.js `serve`:
    ```bash
    # Install serve globally if you haven.t already
    npm install -g serve
    # Navigate into the zenpwaledger directory
    cd /path/to/zenpwaledger
    # Serve the application
    serve .
    ```
    Or using Python's built-in HTTP server:
    ```bash
    # Navigate into the zenpwaledger directory
    cd /path/to/zenpwaledger
    # Serve the application
    python -m http.server 8000
    ```
    Then open your browser to `http://localhost:5000` (or the port `serve`/Python uses).

## Usage

ZenLedger provides a simple interface for managing your finances:

*   **Dashboard:** Get an overview of your financial health.
*   **Accounts:** Manage your chart of accounts (Assets, Liabilities, Equity, Revenue, Expenses).
*   **Journal Entries:** Record detailed transactions using double-entry principles.
*   **Quick Add:** Use streamlined forms for common transactions like expenses, revenue, and transfers.
*   **Favorites:** Save frequently used transactions for quick entry.
*   **Photo Attachments:** Attach receipts or other images to your transactions.

## Data Persistence

**All your data is stored locally in your browser's IndexedDB.** This means:

*   **Offline-first:** You can use the application even without an internet connection.
*   **Privacy:** Your data never leaves your device unless you explicitly export it.
*   **Browser-dependent:** Your data is tied to the specific browser and device you are using. Clearing browser data (especially "site data" or "IndexedDB") will delete your ZenLedger data.

### Backup and Restore

ZenLedger includes built-in features for data management:

*   **Automatic LocalStorage Backup:** A debounced backup is automatically saved to your browser's `localStorage`. This can be restored from the Settings page.
*   **Manual JSON Export/Import:** You can manually export your entire dataset as a JSON file and import it later on any device/browser.
*   **Diff-based Folder Backup (Desktop Browsers):** For supported desktop browsers (e.g., Chrome, Edge), you can set a local folder for automatic, versioned JSON backups using the File System Access API. This provides a robust history of your data.

## Important Notes

*   **Browser Compatibility:** While designed as a PWA, features like "Diff-based Folder Backup" rely on modern browser APIs (File System Access API) which might not be available in all browsers (e.g., Firefox, Safari).
*   **Security:** Keep your device secure. Since data is stored locally, physical access to your device could compromise your financial data.
*   **No Cloud Sync:** There is no built-in cloud synchronization. For multi-device usage, you must manually export and import data.
*   **Double-Entry Accounting:** Familiarity with basic double-entry accounting principles (Debits and Credits) is beneficial for advanced journal entries. An explanation is available within the app.