# AGENT.md — mohamedallam13 (Personal GitHub Profile)

## What this directory is

This is the local clone of all 47 repositories under the GitHub account **mohamedallam13** (Mohamed Allam, personal account). They live at:

```
~/Documents/Code/mohamedallam13/<repo-name>/
```

This is a **personal** account, completely separate from the work account (`mohamed.allam@hellofresh.com` at HelloFresh, Berlin). Both accounts exist on the same machine.

---

## CRITICAL: Git identity

Git identity is automatically scoped via a conditional include in `~/.gitconfig`:

```
[includeIf "gitdir:~/Documents/Code/mohamedallam13/"]
  path = ~/.gitconfig-personal
```

`~/.gitconfig-personal` sets:
- `user.email = mohamedallam.tu@gmail.com`
- `user.name = Mohamed Allam`

**Always verify before committing:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> config user.email
# Must return: mohamedallam.tu@gmail.com
```

Never use `--global` git config changes in this directory. Never commit with the work identity here.

---

## Background and goal

This work started as a profile cleanup project. The goal was to make the GitHub profile (`github.com/mohamedallam13`) look professional — as if a hiring manager or collaborator would look at it and immediately understand who this person is and what they build.

**Mohamed's background:** Originally studied solar energy engineering, transitioned into software development. Now works at HelloFresh in Berlin as a software developer. Specializes in Google Apps Script, internal tooling, and automation — with Node.js and React on the side.

---

## What was done (completed cleanup campaign)

The following was executed across all 47 repos in one campaign:

### Global hygiene (applied to all affected repos)
- **`.DS_Store` removed** from git tracking in 16 repos + added to `.gitignore` in each. A global `~/.gitignore_global` was created so `.DS_Store` is never committed again on this machine.
- **`.clasp.json` removed** from git tracking in 14 GAS repos + added to `.gitignore` in each. `.clasp.json` contains script IDs and is treated as sensitive config — it should never be in git.
- **`node_modules/` removed** from git tracking wherever committed (notably `cc-professionals-network-app/DBUpdate/`).
- **Leaked credentials removed:** `db/dbcredentials.json` in `fantabulous-cli-sql-employee-tracker` contained `{"user":"root","password":"rickandmorty13"}` in plain text in git history. This was removed.
- All 30 affected repos were committed and pushed.

### GitHub profile improvements
- **Bio updated** to: `Solar → Software. I build internal tools, automation pipelines, and web apps. Currently @ HelloFresh, Berlin.`
- **Location** confirmed: Berlin, Germany
- **Profile README** (`mohamedallam13/README.md`) fully rewritten: featured projects table, stack section, contact links. Phone number was intentionally removed.
- **GitHub topics added** to all 44 repos via `gh` CLI.
- `gh` CLI authenticated with `user` scope.

### `cc-professionals-network-app` — full UI rewrite
This was the most significant work. The app is a mental health professionals directory deployed as a GAS Web App. It was completely modernized:

**Before:** Materialize CSS 1.0.0, Materialize teal/black navbar bars, a red "DEV MODE" banner accidentally left in production, a hardcoded old script URL in `card.html`, `console.log()` statements mixed into GAS template tags (literally outputting `console.log(value)` as text into the HTML), `node_modules/` committed to git, `MASTER_INDEX_FILE_ID` duplicated in every function.

**After:**
- Dark glassmorphism design with CSS custom properties (Inter font, `#0d0f14` bg, `#6c63ff` accent)
- Client-side real-time search + topic filter chips (no page reload)
- Custom modal system replacing the third-party MaterialDialog library
- All `console.log` debug statements removed
- DEV MODE banner removed
- Hardcoded old deployment URL replaced with relative `?` param
- GAS template bug fixed (`console.log(<? var ?>)` was invalid mixed syntax)
- `MASTER_INDEX_FILE_ID` extracted to a single top-level constant
- `node_modules/` removed from git, `DBUpdate/.gitignore` created
- `README.md` rewritten with architecture diagram and data flow
- `AGENT.md` created for the repo (see `cc-professionals-network-app/AGENT.md`)

---

## What is NOT done yet (deferred tasks)

### Repo visibility / status cleanup
These decisions were made but not yet executed (requires `gh repo edit`):

| Repo | Decision |
|---|---|
| `cms-style-tech-blog` | Delete — completely empty repo |
| `Horiseon-Services-Website` | Make private — bootcamp exercise, not representative |
| `tailwind-css-example` | Make private — study material only |
| `python-server-examples` | Make private — examples only |
| `demo-addon` | Make private — internal demo |
| `CC-Scripts-KX-V3.0` | Make private — internal scripts, not portfolio-worthy |
| `Coding-Challenge` | Make private — not representative |
| `cc-applications-backend-json-db` | Archive — superseded by `cc-json-db-handler` |

To execute:
```bash
gh repo edit mohamedallam13/<repo> --visibility private
gh repo archive mohamedallam13/cc-applications-backend-json-db
gh repo delete mohamedallam13/cms-style-tech-blog --confirm
```

### Pinned repos
The 6 GitHub profile pin slots are not yet set. Intended pins:
- `afi-online-sales-crm`
- `kroo-mensa-app`
- `kroo-reservation`
- `instapay-receipt-parser`
- `cc-professionals-network-app`
- `react-professional-portfolio`

**Blocker:** GitHub's GraphQL API requires a special token scope (`pin`) to mutate pinned repos, which `gh` CLI does not expose. This requires browser automation (logging into github.com and clicking the pin UI).

### Screenshots
Flagship repos (`afi-online-sales-crm`, `kroo-mensa-app`, `kroo-reservation`, etc.) have no screenshots in their READMEs. Adding screenshots would significantly improve presentation.

### README improvements
Several flagship repos have thin READMEs. The ones most worth improving:
- `afi-online-sales-crm` — no architecture explanation, no screenshots
- `kroo-mensa-app` — no screenshots
- `instapay-receipt-parser` — good README but could add example output

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
| `cc-applications-backend-json-db` | MVC-style backend using JSON files as a DB (ODM pattern) — candidate to archive |
| `cc-json-db-handler` | Drive-backed JSON database API |
| `look-up-tool` | Parameter-based lookup from a preloaded JSON file |
| `CC-AI-Freyal-Bot` | AI bot that receives confessions, generates responses, saves to DB |
| `CC-Scripts-KX-V3.0` | Collection of miscellaneous CC automation scripts — candidate to make private |
| `demo-addon` | Demo Google Docs Add-on — candidate to make private |

### Node.js / backend

| Repo | What it does |
|---|---|
| `fantabulous-cli-sql-employee-tracker` | CLI app — employee management via MySQL |
| `the-amazing-note-taker` | Notes app with Express backend |
| `the-e-commerce-backend` | REST API — e-commerce (Express, MySQL) |
| `the-social-network-api` | REST API — social network (Express, MongoDB) |
| `Read-Me-Generator` | CLI tool that generates README files |
| `profiles-generator-for-teams` | CLI tool that generates HTML employee profile pages |
| `python-server-examples` | Flask and `http.server` examples — candidate to make private |

### Frontend / study projects

| Repo | What it does |
|---|---|
| `smart-weather-app` | Weather app using a weather API |
| `fantastic-daily-calendar` | Daily calendar app with Day.js |
| `jate-texteditor-pwa` | PWA text editor with IndexedDB + service worker |
| `Password-Generator` | Random password generator |
| `Horiseon-Services-Website` | Static company website — candidate to make private |
| `tailwind-css-example` | Tailwind CSS examples — candidate to make private |
| `Coding-Challenge` | Vanilla JS coding challenge webapp — candidate to make private |
| `Professional-Portfolio` | Older non-React portfolio |
| `wikipedia-scraper` | Wikipedia scraper |
| `cms-style-tech-blog` | Empty repo — candidate for deletion |

### Profile / config

| Repo | What it does |
|---|---|
| `mohamedallam13` | GitHub profile README + this AGENT.md |

---

## Technology landscape

The dominant stack is **Google Apps Script (GAS)**. Key patterns used repeatedly across repos:

- **Drive-as-database** — JSON files on Google Drive read/written via `DriveApp`. No SQL, no Firestore.
- **`Toolkit` module** — a shared utility library (`readFromJSON`, `writeToJSON`, `readSheet`, `objectifyArray`, `createTemplateSimple`, etc.) copied (not imported as a library) into each GAS project.
- **`sitePagesManager`** — a router/renderer module (`render()`, `include()`) used in multi-page GAS WebApps to bind server-side variables into HTML templates via `HtmlService`.
- **GAS HTML templating** — `<?= ?>` (escaped output), `<?!= ?>` (raw/unescaped output), `<? ?>` (scriptlet for logic/loops) — all evaluated server-side.
- **`{{ double-brace }}` mustache placeholders** — filled by `Toolkit.createTemplateSimple()` at view-generation time (in DBUpdate scripts), NOT by GAS. These two template systems coexist and must not be confused.
- **Clasp** — used for local ↔ GAS sync. `.clasp.json` is gitignored in all repos.

---

## Global hygiene rules (already applied, must be maintained)

- **`.clasp.json` is gitignored** in all GAS repos — contains script IDs, treat as sensitive config.
- **`.DS_Store` is globally gitignored** via `~/.gitignore_global` — never commit on this machine.
- **`node_modules/` is gitignored** everywhere.
- **No credentials in git** — any file containing passwords, API keys, or tokens must be in `.gitignore`.
- **GitHub topics are set** on all repos — use `gh repo edit --add-topic` to add more.
- **Personal git identity** must be used for all commits here — verified via conditional include (see top of file).

---

## GitHub profile current state

- **Bio:** `Solar → Software. I build internal tools, automation pipelines, and web apps. Currently @ HelloFresh, Berlin.`
- **Location:** Berlin, Germany
- **Website:** set to portfolio URL
- **Profile README:** `mohamedallam13/README.md` — featured projects table, stack section, contact links (no phone number)
- **Pinned repos:** NOT YET SET (see deferred tasks above)
- **Topics:** Set on all 44 repos

---

## Common agent commands

**Check git identity:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> config user.email
# Must return: mohamedallam.tu@gmail.com
```

**Commit and push:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> add -A
git -C ~/Documents/Code/mohamedallam13/<repo> commit -m "message"
git -C ~/Documents/Code/mohamedallam13/<repo> push origin main
```

**Add a GitHub topic:**
```bash
gh repo edit mohamedallam13/<repo> --add-topic <topic>
```

**Make a repo private:**
```bash
gh repo edit mohamedallam13/<repo> --visibility private
```

**Check if a sensitive file is tracked:**
```bash
git -C ~/Documents/Code/mohamedallam13/<repo> ls-files .clasp.json
git -C ~/Documents/Code/mohamedallam13/<repo> ls-files node_modules/
```

**Default branch name:** most repos use `main`, but some older ones use `master` (notably `cc-professionals-network-app`). Always check with `git branch` before pushing.
