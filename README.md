# Privacy Policy

**Design Team Tool** — HTML Element Search Extension  
**Last updated:** July 3, 2026

---

## 1. Overview

Design Team Tool ("the Extension") is a Chrome browser extension built to help designers and developers search for, inspect, and highlight HTML elements on any web page. This Privacy Policy explains how the Extension handles information during its operation.

**The short version:** The Extension does not collect, transmit, store, or share any personal data or browsing data. Everything happens locally in your browser.

---

## 2. Information We Process

The Extension processes the following information **exclusively within your browser and only for the duration of a single search session**:

| Type | Examples | Where it stays |
|---|---|---|
| Search queries you enter | Text, CSS classes, IDs, ARIA labels | In-memory only — cleared on next search |
| Search parameters | Selected scopes, tag filters, match mode | In-memory only — cleared when popup closes |
| Page content of the active tab | HTML element attributes, text content, selectors | In-memory only — never leaves your device |
| Clipboard data | Copied element HTML or result list | Copied only when the user explicitly chooses Copy. Once copied, the content is managed by the operating system's clipboard until it is replaced or cleared by the user. |
| Downloaded files | CSV export of search results | Saved to your local download folder |

None of this information is ever transmitted outside your device.
The Extension never scans webpages in the background; all scans require deliberate user action (pressing a button or enabling the Live Search option).

---

## 3. Information We Do NOT Collect

- ❌ Personal information (name, email, location, etc.)
- ❌ Browsing history
- ❌ Data from tabs other than the one currently being searched
- ❌ Cookies or authentication tokens
- ❌ Crash reports or error logs sent to any server
- ❌ Usage statistics or analytics

---

## 4. Data Storage & Persistence

The Extension does **not** use any form of persistent storage:

- No `localStorage` or `sessionStorage`
- No `IndexedDB` or cookies
- No remote database or backend

All search results and state exist only in memory while the Extension popup is open. Closing the popup discards everything immediately.

---

## 5. Permissions Explained

The Extension requests the following Chrome permission:

### `<all_urls>` (Host Permission)

**Why it is needed:** To search HTML elements on any website you visit, the Extension must inject a lightweight search script into the active page. The `<all_urls>` permission grants access to do this across all websites.

**What it does NOT mean:**
- The Extension does not read your browsing history
- It does not access tabs other than the one you are currently viewing
- It does not transmit page data anywhere

This permission is requested on-demand the first time you perform a search and can be revoked at any time via **Chrome → Settings → Extensions → Design Team Tool → Permissions**.

### Live Search

When the optional **Live Search** feature is enabled by the user, the Extension automatically refreshes search results whenever:

- the HTML document changes, or
- the active browser tab changes.

This monitoring occurs only while the Extension popup is open. Closing the popup immediately stops Live Search.

### Remote Code

The Extension does not download or execute remote JavaScript, WebAssembly, or other executable code. All functionality is packaged within the extension submitted to the Chrome Web Store.

### Other Chrome APIs used

| API | Purpose |
|---|---|
| `chrome.tabs.query` | Identify the currently active tab |
| `chrome.tabs.onActivated / onUpdated` | Detect tab switches to manage live search |
| `chrome.scripting.executeScript` | Inject the search and highlight logic into the active page |
| `chrome.runtime.onMessage` | Receive signals from the page when the DOM changes (live search mode) |
| `chrome.permissions.contains / request` | Request `<all_urls>` permission when first needed |
| `chrome.downloads.download` | Save CSV exports to your Downloads folder |

All of these APIs are used **locally** and their output never leaves your device.

---

## 6. Third-Party Services

The Extension does **not** integrate with any third-party services. There are no:

- Analytics platforms (e.g. Google Analytics, Mixpanel)
- Error tracking services (e.g. Sentry, Bugsnag)
- Advertising networks
- Remote backend APIs

The only runtime dependencies are **Vue 3** and **Pinia**, which are bundled into the extension package and execute entirely on your device.

---

## 7. Data Sharing

We do not sell, rent, or share any data with any third parties because we do not collect any data in the first place.

---

## 8. Children's Privacy

The Extension is a developer utility and is not directed at children under the age of 13. It does not collect any information from any user, regardless of age.

---

## 9. Security

Because the Extension processes all information locally and never transmits data externally, there is no network surface to secure. The Chrome extension security model (process isolation, permission prompts) applies as enforced by the browser.

---

## 10. Changes to This Policy

If the Extension's data practices change in a future version (e.g. a cloud sync feature is added), this Privacy Policy will be updated and the "Last updated" date at the top will reflect the change. Significant changes will be noted in the extension's release notes.

---

## 11. Contact

If you have questions about this Privacy Policy, please open an issue on the project repository:

**GitHub:** [WitoldRykowski/design-team-tool](https://github.com/WitoldRykowski/design-team-tool)

---

*This Privacy Policy applies to Design Team Tool version 0.0.0 and later.*
