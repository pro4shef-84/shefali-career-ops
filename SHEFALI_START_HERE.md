# Shefali — Start Here

Hi Shef! This is your personal job-search command center, set up and pre-loaded with your CV, target portals, and current pipeline. Everything below assumes Claude Code is already installed on your Mac.

---

## 1. Clone this repo

```bash
git clone https://github.com/pro4shef-84/shefali-career-ops.git ~/career-ops
cd ~/career-ops
npm install
```

That's it for setup. No env file is required unless you want to use the optional Gemini-based scorer (see step 5).

---

## 2. What's already in here for you

| File / Folder | What it is |
|---|---|
| `cv.md` | Your master resume in Markdown. Edit this — generated PDFs and DOCX files flow from it. |
| `data/applications.md` | Tracker for jobs you've applied to. |
| `data/pipeline.md` | Inbox — paste job URLs here, then process them with `/career-ops`. |
| `portals.yml` | Pre-configured list of job boards to scan. |
| `jds/` | Saved job descriptions you've evaluated. |
| `interview-prep/` | Notes and prep material for upcoming interviews. |
| `output/` | Generated resumes (PDF, DOCX) per role. |
| `modes/` | The Claude Code skill that powers `/career-ops` commands. |

---

## 3. Daily workflow

Open Claude Code inside this folder:

```bash
cd ~/career-ops
claude
```

Then in Claude Code, use the slash command:

```
/career-ops
```

That launches your job-search assistant. From there you can:

- **Scan portals** — find new openings matching your background
- **Evaluate a JD** — paste a URL or job text, get a fit score + tailored resume
- **Track applications** — update statuses, log follow-ups
- **Generate a tailored resume** — PDF or DOCX customized to a specific role

---

## 4. Add jobs to your pipeline

Paste job URLs into `data/pipeline.md` under the `## Pendientes` section, one per line. Then in Claude Code:

```
/career-ops pipeline
```

It will fetch, score, and queue them for your review.

---

## 5. Optional: enable the Gemini scorer

The Gemini integration gives a free second-opinion fit score on each JD.

1. Get a free API key: https://aistudio.google.com/apikey
2. Copy `.env.example` to `.env`
3. Paste the key into `GEMINI_API_KEY=`

Without this, everything still works — you just won't get the Gemini score column.

---

## 6. Keeping up to date

This repo is forked from the public `santifer/career-ops` project. To pull in upstream improvements:

```bash
git fetch upstream
git merge upstream/main
```

Your private data (cv.md, data/, jds/, output/, interview-prep/) won't be touched by upstream changes.

---

## 7. Useful commands

```bash
npm run doctor          # Health check — confirms everything is wired up
npm run scan            # Scan portals.yml for new postings
node generate-pdf.mjs   # Regenerate cv.pdf from cv.md
```

---

## Questions?

This whole thing runs locally on your machine — your data never leaves your Mac unless you push it back to GitHub. If anything breaks or feels off, open Claude Code in this folder and just describe what you want — it knows the project structure.

Good luck with the search! 🎯
