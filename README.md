# 💼 Ganesh Putran — Portfolio

Personal portfolio site for Ganesh Putran, DevOps Engineer.

**Live:** [noobstar2306.github.io](https://noobstar2306.github.io)

---

## Architecture

This repo is the **appearance layer only** — pure HTML and CSS with zero JavaScript logic, zero API keys, and zero business logic. All interactive features are loaded from the [ai-devops-bot](https://github.com/noobstar2306/ai-devops-bot) repo via a single script tag:

```html
<script src="https://noobstar2306.github.io/ai-devops-bot/widgets.js"></script>
```

This separation means:
- Updating a feature → edit `widgets.js` in `ai-devops-bot` — no changes needed here
- Updating the design → edit `index.html` here — functionality untouched
- No API keys ever in this repo

---

## Structure

```
noobstar2306.github.io/
│
├── index.html              # Portfolio — appearance only (441 lines)
└── .github/workflows/
    └── deploy.yml          # Deploys to GitHub Pages (no secret injection needed)
```

---

## Features loaded from widgets.js

All functionality is served from `ai-devops-bot` via the Cloudflare Worker proxy. No keys are injected here.

| Feature | Description |
|---------|-------------|
| 💡 AI tips | Gemini-generated DevOps tips via Cloudflare Worker |
| ❓ Help modal | GitHub issue creator with bug/suggestion routing |
| 🎯 Hobbies button | Links to the hobbies & interests page |
| 📖 README tooltip | Shows repo README on hover over help button |
| ⚙️ Skills grid | 10 tech + 6 soft skill cards rendered dynamically |
| 🎨 Scroll reveal | Cards fade in as you scroll down |

---

## Issue routing

The ❓ help button routes issues to the correct repo automatically:

| Issue type | Destination |
|-----------|-------------|
| 🐛 Bug / ❓ Question | `noobstar2306/ai-devops-bot` |
| 💡 Suggestion / ✨ Improvement | `noobstar2306/noobstar2306.github.io` |

---

## Deployment

Pushes to `main` trigger the **Deploy Portfolio** workflow:
1. Checkout code
2. Configure GitHub Pages
3. Upload `index.html` to GitHub Pages
4. Deploy

**No secret injection** — all API calls go through the Cloudflare Worker in `ai-devops-bot`. This repo requires zero GitHub Secrets.

---

## Linked repos

| Repo | Purpose |
|------|---------|
| [ai-devops-bot](https://github.com/noobstar2306/ai-devops-bot) | All functionality — dashboard, hobbies, widgets, CI pipeline, Cloudflare Worker |

---

## Full documentation

- [Project wiki](https://github.com/noobstar2306/ai-devops-bot/wiki) — architecture, features, security, roadmap
- [Project documentation](https://github.com/noobstar2306/ai-devops-bot/blob/main/PROJECT_DOCUMENTATION.md) — comprehensive technical report

---

## Author

**Ganesh Putran**
- GitHub: [noobstar2306](https://github.com/noobstar2306)
- LinkedIn: [ganesh-putran](https://www.linkedin.com/in/ganesh-putran-b047ba235/)
- Dashboard: [noobstar2306.github.io/ai-devops-bot](https://noobstar2306.github.io/ai-devops-bot/)
- Hobbies: [noobstar2306.github.io/ai-devops-bot/hobbies.html](https://noobstar2306.github.io/ai-devops-bot/hobbies.html)
