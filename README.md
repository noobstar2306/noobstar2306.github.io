# 💼 Ganesh Putran — Portfolio

Personal portfolio site for Ganesh Putran, DevOps Engineer.

**Live:** [noobstar2306.github.io](https://noobstar2306.github.io)

---

## Architecture

This repo is the **appearance layer only** — pure HTML and CSS with no hardcoded functionality or API keys. All interactive features (AI tips, help modal, skills rendering, hobbies button) are loaded from the [ai-devops-bot](https://github.com/noobstar2306/ai-devops-bot) repo via a single script tag:

```html
<script src="https://noobstar2306.github.io/ai-devops-bot/widgets.js"></script>
```

This separation means:
- Updating a feature → edit `widgets.js` in `ai-devops-bot` only
- Updating the design → edit `index.html` here only
- No risk of breaking functionality when changing appearance

---

## Structure

```
noobstar2306.github.io/
│
├── index.html              # Portfolio — appearance only
└── .github/workflows/
    └── deploy.yml          # Injects secrets, deploys to GitHub Pages
```

---

## Features loaded from widgets.js

| Feature | Description |
|---------|-------------|
| 💡 AI tips | Gemini-generated DevOps tips on demand |
| ❓ Help modal | GitHub issue creator with repo routing |
| 🎯 Hobbies button | Links to the hobbies & interests page |
| 📖 README tooltip | Shows repo README on hover over help button |
| ⚙️ Skills grid | Tech and soft skills rendered dynamically |

---

## Deployment

Pushes to `main` trigger the Deploy Portfolio workflow which:
1. Injects `GEMINI_TIPS_KEY` and `GH_PAT` from GitHub Secrets into `index.html`
2. Deploys to GitHub Pages

### GitHub Secrets required

| Secret | Purpose |
|--------|---------|
| `GEMINI_TIPS_KEY` | Gemini API key for AI tips (injected into widgets.js at deploy) |
| `GH_PAT` | GitHub PAT for issue creation (injected into widgets.js at deploy) |

---

## Linked repos

| Repo | Purpose |
|------|---------|
| [ai-devops-bot](https://github.com/noobstar2306/ai-devops-bot) | All functionality — dashboard, hobbies, widgets, CI pipeline |

---

## Author

**Ganesh Putran**
- GitHub: [noobstar2306](https://github.com/noobstar2306)
- LinkedIn: [ganesh-putran](https://www.linkedin.com/in/ganesh-putran-b047ba235/)
- Dashboard: [noobstar2306.github.io/ai-devops-bot](https://noobstar2306.github.io/ai-devops-bot/)
