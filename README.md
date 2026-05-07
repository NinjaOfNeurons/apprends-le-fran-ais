# 🇫🇷 French Essentials Quiz

> An AI-powered French language learning app built on the *Learn French With Alexa* — French Essentials series (Lessons 1–20).

![Stage](https://img.shields.io/badge/stage-v0.1%20MVP-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![HTML](https://img.shields.io/badge/built%20with-HTML%2FCS%2FJS-orange)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)

---

## 📍 Current Stage — v0.1 MVP (Static Quiz)

The app is currently a **fully functional, single-file static HTML quiz** requiring zero dependencies, zero build steps, and zero server. Open it in any browser and it works.

### What's working right now

- **500 hand-crafted questions** across all 20 lesson topics
- **Topic filtering** — study one topic or mix them all
- **Configurable session length** — 20, 50, 100, or all 500 questions
- **Randomised question and answer order** on every session
- **Instant feedback** with correct answer revealed on wrong attempts
- **Live score tracking** and a results summary screen
- **Fully responsive** — works on desktop and mobile browsers
- **Zero dependencies** — one `.html` file, open and play

### Known limitations at this stage

- No persistence — scores reset on every page refresh
- Questions are static — fixed set of 500, no dynamic generation
- No progress tracking across sessions
- No user accounts or profiles
- No CI/CD, no tests, no containerisation

---

## 🗺️ Roadmap

### v0.2 — Persistence & Progress Tracking
> *Target: local storage + a learning dashboard*

- [ ] Save scores and session history to `localStorage`
- [ ] Learning dashboard showing:
  - Per-topic accuracy over time
  - Total questions answered
  - Weak areas highlighted
  - Study streak counter (days in a row)
- [ ] Mark questions as "needs review" and resurface them
- [ ] Export progress as JSON

---

### v0.3 — Spaced Repetition Engine
> *Target: smarter studying*

- [ ] Implement an SM-2 spaced repetition algorithm
- [ ] Questions you get wrong come back sooner
- [ ] Questions you consistently get right are retired temporarily
- [ ] "Daily review" mode — the app tells you what to study today
- [ ] Difficulty rating per question (Easy / Hard)

---

### v0.4 — AI-Powered Question Generation (Anthropic API)
> *Target: unlimited questions, personalised to your gaps*

- [ ] Integrate Anthropic Claude API (`claude-sonnet-4-6`)
- [ ] Dynamically generate new questions on any topic on demand
- [ ] AI explanation mode — when you get an answer wrong, Claude explains *why* in context with examples
- [ ] Generate custom quizzes from a user-provided topic or vocabulary list
- [ ] Difficulty-adaptive question generation based on past performance
- [ ] Safe API key handling via backend proxy (no keys exposed in frontend)

---

### v0.5 — Audio & Pronunciation
> *Target: listening and speaking practice*

- [ ] Text-to-speech for every question and answer using the Web Speech API
- [ ] Speech recognition — answer questions out loud
- [ ] Pronunciation scoring (phoneme comparison)
- [ ] Audio for French vocabulary words

---

### v0.6 — DevOps & Production Hardening
> *Target: CI/CD, Docker, tested, deployable*

- [ ] Refactor into a proper project structure:
  ```
  french-essentials-quiz/
  ├── .github/
  │   └── workflows/
  │       ├── ci.yml          # lint + test on PR
  │       └── deploy.yml      # auto-deploy to GitHub Pages on merge
  ├── src/
  │   ├── data/
  │   │   └── questions.json  # questions extracted to data file
  │   ├── js/
  │   │   ├── quiz.js
  │   │   ├── dashboard.js
  │   │   └── spaced-rep.js
  │   └── css/
  │       └── style.css
  ├── tests/
  │   ├── quiz.test.js
  │   └── e2e/
  │       └── quiz.spec.ts    # Playwright end-to-end tests
  ├── Dockerfile
  ├── docker-compose.yml
  ├── Makefile
  ├── README.md
  └── index.html
  ```
- [ ] Dockerise with Nginx for self-hosting
- [ ] GitHub Actions CI pipeline (lint, unit tests, e2e tests)
- [ ] GitHub Actions CD pipeline (auto-deploy to GitHub Pages)
- [ ] Playwright end-to-end tests for core quiz flows
- [ ] Jest unit tests for quiz logic, spaced repetition, score calculation
- [ ] Semantic versioning + auto-generated `CHANGELOG.md`
- [ ] `Makefile` with `make dev`, `make test`, `make deploy`
- [ ] Build status, coverage, and live demo badges in README

---

### v1.0 — Full AI Learning Platform
> *Target: shareable, multi-user, production-grade*

- [ ] Backend API (Node.js / FastAPI) for user accounts and persistent cloud storage
- [ ] Authentication (GitHub OAuth or email/password)
- [ ] Multi-user leaderboards
- [ ] Lesson progress tied to the full Alexa series (beyond Lesson 20)
- [ ] Admin panel to add/edit questions
- [ ] Public API for other developers to build on
- [ ] Mobile app wrapper (PWA or React Native)

---

## 🛠️ Tech Stack

| Layer | Current (v0.1) | Planned |
|---|---|---|
| Frontend | Vanilla HTML/CSS/JS | Stays vanilla or migrates to React |
| Data | Inline JS array | `questions.json` + dynamic API |
| AI | None | Anthropic Claude API (claude-sonnet-4-6) |
| Storage | None | localStorage → PostgreSQL |
| Backend | None | Node.js / FastAPI |
| CI/CD | None | GitHub Actions |
| Hosting | Static file | GitHub Pages → Docker + VPS |
| Testing | None | Jest + Playwright |

---

## 🚀 Getting Started

### v0.1 (current) — just open the file

```bash
git clone https://github.com/YOUR_USERNAME/french-essentials-quiz.git
cd french-essentials-quiz
open index.html   # or double-click the file
```

No install. No build. No server required.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first to discuss what you'd like to change.

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/spaced-repetition`)
3. Commit your changes (`git commit -m 'feat: add SM-2 spaced repetition'`)
4. Push to the branch (`git push origin feature/spaced-repetition`)
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

---

## 📚 Based On

[Learn French With Alexa](https://www.youtube.com/@learnfrenchwithalexa) — French Essentials series, Lessons 1–20.

Topics covered: Greetings · Numbers · Alphabet · Days · Months · Weather & Seasons · Definite Articles · Indefinite Articles · Subject Pronouns · Être & Avoir · Aller + Prepositions · French Prepositions · Negation (parts 1 & 2) · Telling the Time (parts 1 & 2) · French Accents (parts 1–4)

---

## 📄 License

[MIT](LICENSE)
