<div align="center">

# Sentilis Content 📚

**The official content repository for [Sentilis](https://sentilis.me) — documentation, templates, and examples for Press, Market, and Bio.**

Write in Markdown. Push to `main`. Your content goes live on Sentilis automatically.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Powered by Sentilis](https://img.shields.io/badge/Powered%20by-Sentilis-FA8072.svg)](https://sentilis.me)

</div>

---

## ✨ What's Inside

| Folder | What it holds |
|---|---|
| 📰 [`en/press/`](./en/press) · [`es/press/`](./es/press) | **Press** — blog posts, press releases, changelogs, and product docs. |
| 🛒 [`en/market/`](./en/market) · [`es/market/`](./es/market) | **Market** — service listings, physical products, and digital downloads. |
| 💼 [`en/bio/`](./en/bio) · [`es/bio/`](./es/bio) | **Bio** — professional profiles for people and companies. |
| 🧩 [`en/templates/`](./en/templates) | **Templates** — copy-paste starters for every content type. |

---

## 🚀 Quickstart

Pick what you want to publish, drop a Markdown file in the right folder, push to `main`:

| You want to… | Create a file in… | Read the guide |
|---|---|---|
| Share a blog post or announcement | `en/press/my-post.md` | [Press guide](https://sentilis.me/en/press/what-is-sentilis-press-69f1aa4c8d8ef9e4cd7491c8) |
| List a service, product, or download | `en/market/my-thing.md` | [Market guide](https://sentilis.me/en/press/what-is-sentilis-market-6a016eba550ca18de6066893) |
| Publish your resume or company profile | `en/bio/my-profile.md` | [Bio guide](https://sentilis.me/en/press/what-is-sentilis-bio-6a016eb9550ca18de606688f) |

The GitHub Actions workflow detects what changed, authenticates with your profile token, and syncs everything to Sentilis. 🎉

---

## 🧩 Templates

- 💼 Bio: Software Developer, US Startup
- 🛒 Market: Service, Physical Product, Digital Download
- 📰 Press: Press Release, Blog Post, Changelog

---

## ⚙️ CI/CD Setup

Publishing is wired up via [`.github/workflows/sentilis-sync.yml`](./.github/workflows/sentilis-sync.yml). Two parallel jobs run on every push to `main`:

| Job | Profile | Folder synced | Required secret |
|---|---|---|---|
| `sync-en` | English (Profile 1) | `./en` | `SENTILIS_TOKEN_EN` |
| `sync-es` | Spanish (Profile 2) | `./es` | `SENTILIS_TOKEN_ES` |

### Configure the secrets

1. Go to **Settings → Secrets and variables → Actions → New repository secret**.
2. Create `SENTILIS_TOKEN_EN` with your English profile token.
3. Create `SENTILIS_TOKEN_ES` with your Spanish profile token.

> 🔒 Tokens are never logged. The workflow uses `secrets.*` substitution so GitHub redacts them automatically.

### Trigger conditions

- **`push` to `main`** — publishes changes in `en/**` or `es/**`.
- **`pull_request` to `main`** — runs a dry validation (catches broken frontmatter early).
- **`workflow_dispatch`** — manual re-sync from the Actions tab.

---

## 🛠️ Local Development

Want to validate before pushing? Install the CLI locally:

```bash
npm install -g @sentilis/cli

# Authenticate once
sentilis auth login <your-token>

# Sync a profile directory
sentilis sync ./en --strict
sentilis sync ./es --strict
```

The `--strict` flag treats warnings as errors — great for catching typos in frontmatter, broken local links, or missing attachments before they hit production.

---

## 📂 Repository Layout

```text
sentilis.content/
├── en/                                # English profile
│   ├── bio/                           # Bio entries
│   ├── market/                        # Market entries
│   ├── press/                         # Press entries (incl. docs)
│   │   ├── bio/                       # → Bio user guide
│   │   ├── market/                    # → Market user guide
│   │   └── press/                     # → Press user guide
│   └── templates/                     # Copy-paste templates
├── es/                                # Spanish profile (same layout)
├── .github/workflows/
│   └── sentilis-sync.yml              # GitHub Actions publisher
├── LICENSE                            # MIT
└── README.md
```

---

## 🤝 Contributing

This repo is open source under the MIT license. Spotted a typo, want to suggest a new template, or improve a doc?

1. Fork the repo.
2. Create a branch (`fix/typo-in-bio-docs` or `feat/template-podcast-episode`).
3. Open a pull request against `main`.

PRs that touch `en/**` or `es/**` automatically trigger a dry-run validation in CI — no surprises after merge.

---

## 🔗 Links

- 🌐 **Sentilis (EN):** <https://sentilis.me/en>
- 🌐 **Sentilis (ES):** <https://sentilis.me/es>
- 📦 **CLI:** <https://github.com/sentilis/cli>
- 🧠 **Core:** <https://github.com/sentilis/core>
- ✍️ **Obsidian plugin:** <https://github.com/sentilis/obsidian>

---

## 📄 License

[MIT](./LICENSE) © 2026 Sentilis
