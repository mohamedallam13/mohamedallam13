# AGENT.md — mohamedallam13 (Personal GitHub Profile)

## What this directory is

This is the local clone of all 47 repositories under the GitHub account **mohamedallam13** (Mohamed Allam, personal account). They live at:

```
~/Documents/Code/mohamedallam13/<repo-name>/
```

This is a **personal** account, separate from the work account (`mohamed.allam@hellofresh.com`). Git identity is automatically applied via a conditional include in `~/.gitconfig`:

```
[includeIf "gitdir:~/Documents/Code/mohamedallam13/"]
  path = ~/.gitconfig-personal
```

**Always verify `git log --format="%ae" -1` shows `mohamedallam.tu@gmail.com` before committing in any of these repos.**

---

## Repository index

### Flagship / actively maintained

| Repo | What it does | Stack |
|---|---|---|
| `afi-online-sales-crm` | CRM for managing customers, orders and leads at AFI | GAS, JS, HTML |
| `kroo-mensa-app` | Menu ordering system for KROO coworking space cafe | GAS, JS, HTML |
| `kroo-reservation` | Room booking system (guest / user / admin modes) | GAS, JS, HTML |
| `kroo-mgmt-app` | Coworking space management: QR check-ins, billing | GAS, JS, HTML |
| `kroo-cafe-pos` | Point-of-sale for a cafe | GAS, JS, HTML |
| `kroo-checklists` | Operator checklists webapp | GAS, JS, HTML |
| `cc-professionals-network-app` | Mental health professionals directory with search/filter | GAS, JS, HTML |
| `instapay-receipt-parser` | GCP Cloud Function — OCR parsing of Instapay receipts | GCP, Document AI, Node.js |
| `feryal-slack-bot` | Slack bot integrated with Google Sheets/Docs/Forms | GAS, Slack API |
| `gas-auto-invoicing-script` | Auto-generates HTML invoices from Sheets | GAS, JS |
| `react-professional-portfolio` | Personal portfolio, live on GitHub Pages | React, JS |

### Google Apps Script tools (internal / domain-specific)

| Repo | What it does |
|---|---|
| `afi-erp-orders-form` | Supply order management for Advanced Food Industries |
| `afi-machinery-app` | Machinery maintenance tracking |
| `gas-jobs-application-tracking` | Automates job application pipeline from Sheets/Docs/Forms |
| `gas-invoices-tool` | Invoice submission WebApp |
| `gas-webform-scriplets` | Webform built with GAS scriptlets to emulate a component model |
| `cc-community-webapp` | Community web app with GAS HTML templating |
| `cc-conf-tracking-tool` | Submission/status tracking WebApp |
| `cc-confessions-lookup` | Text-match lookup against a JSON file DB |
| `cc-event-manage-app` | Event creation and Sheets/Forms management |
| `cc-general-filtering-tool` | Admin filtering tool for fan/community submissions |
| `cc-posting-tool` | Filters fan submissions and queues posts for Facebook |
| `cc-professionals-webapp` | Earlier version of the professionals directory |
| `cc-applications-backend-json-db` | MVC-style backend using JSON files as a DB (ODM pattern) |
| `cc-json-db-handler` | Drive-backed JSON database API |
| `look-up-tool` | Parameter-based lookup from a preloaded JSON file |
| `CC-AI-Freyal-Bot` | AI bot that receives confessions, generates responses, saves to DB |
| `CC-Scripts-KX-V3.0` | Collection of miscellaneous CC automation scripts |
| `demo-addon` | Demo Google Docs Add-on |

### Node.js / backend

| Repo | What it does |
|---|---|
| `fantabulous-cli-sql-employee-tracker` | CLI app — employee management via MySQL |
| `the-amazing-note-taker` | Notes app with Express backend |
| `the-e-commerce-backend` | REST API — e-commerce (Express, MySQL) |
| `the-social-network-api` | REST API — social network (Express, MongoDB) |
| `Read-Me-Generator` | CLI tool that generates README files |
| `profiles-generator-for-teams` | CLI tool that generates HTML employee profile pages |
| `python-server-examples` | Flask and `http.server` examples |

### Frontend / study projects

| Repo | What it does |
|---|---|
| `smart-weather-app` | Weather app using a weather API |
| `fantastic-daily-calendar` | Daily calendar app with Day.js |
| `jate-texteditor-pwa` | PWA text editor with IndexedDB + service worker |
| `Password-Generator` | Random password generator |
| `Horiseon-Services-Website` | Static company website |
| `tailwind-css-example` | Tailwind CSS examples |
| `Coding-Challenge` | Vanilla JS coding challenge webapp |
| `Professional-Portfolio` | Older non-React portfolio |
| `wikipedia-scraper` | Wikipedia scraper |

### Profile / config

| Repo | What it does |
|---|---|
| `mohamedallam13` | GitHub profile README |

---

## Technology landscape

The dominant stack across this portfolio is **Google Apps Script (GAS)**. Key GAS patterns used repeatedly:

- **Drive-as-database** — JSON files on Google Drive read/written via `DriveApp`. No SQL.
- **`Toolkit` module** — a shared utility library (`readFromJSON`, `writeToJSON`, `readSheet`, `objectifyArray`, etc.) that is copied (not imported) into each GAS project.
- **`sitePagesManager`** — a router/renderer module (`render()`, `include()`) used in multi-page GAS WebApps to bind server-side variables into HTML templates.
- **GAS HTML templating** — `<?= ?>` (escaped), `<?!= ?>` (raw), `<? ?>` (scriptlet) tags evaluated server-side by `HtmlService`.
- **Clasp** — used for local ↔ GAS sync. `.clasp.json` is gitignored in all repos.

---

## Global git / repo hygiene rules

These rules were applied across all repos and must be maintained:

- **`.clasp.json` is gitignored** in all GAS repos (contains script IDs — treat as sensitive config).
- **`.DS_Store` is globally gitignored** via `~/.gitignore_global`.
- **`node_modules/` is gitignored** in all repos that have one.
- **No credentials in git** — `db/dbcredentials.json` was removed from `fantabulous-cli-sql-employee-tracker` history.
- **GitHub topics** are set on all repos (use `gh repo edit --add-topic` to add more).

---

## Repos with known issues / deferred tasks

| Repo | Issue |
|---|---|
| `cms-style-tech-blog` | Empty repo — candidate for deletion |
| `Horiseon-Services-Website` | Candidate to make private (bootcamp exercise) |
| `tailwind-css-example` | Candidate to make private (study material) |
| `python-server-examples` | Candidate to make private (examples only) |
| `demo-addon` | Candidate to make private |
| `CC-Scripts-KX-V3.0` | Candidate to make private (internal scripts) |
| `Coding-Challenge` | Candidate to make private |
| `cc-applications-backend-json-db` | Candidate to archive |

---

## GitHub profile state

- **Bio:** `Solar → Software. I build internal tools, automation pipelines, and web apps. Currently @ HelloFresh, Berlin.`
- **Location:** Berlin, Germany
- **Profile README:** `mohamedallam13/README.md` — includes featured projects table, stack, contact links
- **Pinned repos:** Not yet set (requires browser automation — GitHub's GraphQL API does not expose pinned repo mutation without a token with specific scopes)

---

## Common agent tasks in this directory

**Adding a topic to a repo:**
```bash
gh repo edit mohamedallam13/<repo> --add-topic <topic>
```

**Checking git identity before committing:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> config user.email
# Must return: mohamedallam.tu@gmail.com
```

**Pushing a change:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> add -A
git -C ~/Documents/Code/mohamedallam13/<repo> commit -m "message"
git -C ~/Documents/Code/mohamedallam13/<repo> push origin main
```

**Checking if a file is tracked that shouldn't be (e.g. .clasp.json):**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> ls-files .clasp.json
```
