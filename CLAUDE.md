# Resume — CLAUDE.md

## What This Repo Is

LaTeX-based single-page resume for Shubham Chadokar, a 10-year backend platform engineer.
Source: `main.tex` (sb2nov/resume template, MIT License)
Output: `main.pdf` (committed to repo, served via `index.html`)

## Building

```bash
# Preferred — auto-detects aux files, runs multiple passes
latexmk -pdf main.tex

# Or single pass (may need running twice for references)
pdflatex main.tex
```

Build artifacts (`main.aux`, `main.log`, `main.out`, `main.synctex.gz`) are gitignored.

**VS Code:** Install LaTeX Workshop extension. It auto-compiles on save.

## File Map

| File        | Purpose                              |
|-------------|--------------------------------------|
| main.tex    | Single source of truth for resume    |
| main.pdf    | Compiled output — commit after build |
| index.html  | Redirects web viewers to main.pdf    |
| README.md   | Human-facing setup instructions      |

## Resume Sections (in order in main.tex)

1. **Header** — name, phone, email, LinkedIn, GitHub, portfolio
2. **Summary** — 2–3 sentence career narrative
3. **Experience** — reverse-chronological, `\resumeSubheading` + `\resumeItemListStart`
4. **Projects** — `\resumeProjectHeading` entries
5. **Writing & Speaking** — publications, conferences
6. **Education** — single entry
7. **Technical Skills** — grouped by category (Languages, Infra & Data, Frameworks & Tools)

## Custom LaTeX Commands

```latex
\resumeItem{text}                          % Single bullet
\resumeSubheading{Title}{Date}{Company}{Location}
\resumeProjectHeading{Project (link)}{Date}
\resumeItemListStart ... \resumeItemListEnd % Wraps bullet list
```

## Editing Guidelines

- **Keep it one page.** Never let content overflow. Cut bullets before adding.
- **Metrics first.** Every bullet should lead with a number or outcome if possible.
  - Good: "Reduced billing latency by 60%, cutting infra cost by 30%"
  - Bad: "Worked on billing system improvements"
- **Tense:** Past tense for all roles except current one (present tense).
- **Active voice.** Start bullets with strong verbs: Architected, Reduced, Led, Shipped.
- **ATS-safe:** No tables inside experience bullets, no images, no non-standard Unicode.
- **Font:** Default article 11pt. Do not change without checking PDF output fits one page.

## Workflow for Changes

1. Edit `main.tex`
2. Build: `latexmk -pdf main.tex`
3. Inspect `main.pdf` — verify single page, no overflows, correct formatting
4. Commit both `main.tex` and `main.pdf`

```bash
git add main.tex main.pdf
git commit -m "resume: <what changed>"
```

## What NOT to Do

- Do not add LaTeX packages without verifying they are available in the user's TeX distro.
- Do not use `\\` for line breaks inside bullet items — use `\resumeItem` instead.
- Do not commit `.aux`, `.log`, `.out`, or `.synctex.gz` files.
- Do not reformat the entire document — small, targeted edits only.
- Do not shrink margins or font size to fit more content — cut content instead.

## How Claude Should Help

Claude's primary role in this repo is to **write and improve resume content**. Treat every request as coming from a senior staff engineer who knows their work deeply but needs help articulating it with maximum impact.

### Writing New Bullets

When the user describes something they did, convert it into a strong resume bullet:
1. Lead with a metric or outcome if one exists — ask if none is provided
2. Use the STAR-lite format: Action → System/Scale → Result
3. Strip filler: "helped", "worked on", "involved in", "responsible for"
4. Keep under 120 characters so it fits on one line in the PDF

Example transformation:
- Raw: "I fixed a MongoDB issue where there were too many collections"
- Improved: `Resolved MongoDB file-descriptor exhaustion by consolidating 100K+ collections, eliminating repeated production incidents`

### Improving Existing Bullets

When asked to improve a bullet:
1. Read the surrounding role context first (company, title, dates)
2. Strengthen the verb, sharpen the metric, tighten the phrasing
3. Offer 2–3 variants when the direction isn't clear
4. Never add claims the user didn't provide — ask instead

### Tailoring for a Job Description

When given a JD:
1. Identify the top 5 keywords/requirements from the JD
2. Check which bullets in the resume already cover them
3. Suggest rewording existing bullets to surface matching signals — do not fabricate experience
4. Flag any required skills completely absent from the resume

### Asking for Missing Info

If a bullet lacks a metric, ask one focused question:
> "Do you have a number for this? (e.g., latency reduction %, throughput, team size, time saved)"

Do not invent numbers. If the user says they don't know, write the bullet without a metric but flag it as weak.

### Section-Specific Guidance

- **Summary:** Must name the domain (distributed systems / platform eng), years of experience, and 1–2 signature achievements. 2 sentences max.
- **Experience bullets:** 3–5 bullets per role. Most recent role gets the most detail.
- **Projects:** Lead with the problem solved, not the tech used.
- **Skills:** Only list technologies with real production experience — ask before adding anything new.

## Owner Context

- **Current role:** Senior Software Engineer, Data Engineering at Infoblox (Sept 2024–present)
- **Domain expertise:** Distributed systems, Kafka, Kubernetes, Go, PostgreSQL, observability
- **Career narrative:** Platform engineer who ships high-throughput, low-latency systems and simplifies complex infrastructure
- **Tone:** Technically precise, metric-driven, no buzzword fluff
