# Resume Template

A clean, single-page LaTeX resume template for software engineers.

- **Author:** Shubham Chadokar
- **Based on:** [sb2nov/resume](https://github.com/sb2nov/resume)
- **License:** MIT

---

## Preview

The compiled PDF is included as `main.pdf` for quick reference.

---

## Prerequisites

Install a LaTeX distribution for your OS:

| OS | Distribution | Download |
|----|-------------|---------|
| macOS | MacTeX | https://www.tug.org/mactex/ |
| Windows | MiKTeX | https://miktex.org/ |
| Linux | TeX Live | `sudo apt install texlive-full` |

---

## Editing the Template

Open `main.tex` and update the following sections with your information:

1. **Header** — name, phone, email, LinkedIn, GitHub
2. **Education** — institution, degree, dates
3. **Experience** — company, title, dates, bullet points
4. **Projects** — project name, tech stack, description
5. **Skills** — languages, frameworks, tools, platforms

### Tips

- Keep bullet points concise and action-oriented (Led, Built, Reduced, Improved)
- Stick to one page — adjust `\addtolength{\textheight}` in the preamble if content overflows
- Uncomment a font package in the `FONT OPTIONS` section to change the typeface

---

## Building the PDF

### Option 1: VS Code with LaTeX Workshop (Recommended)

1. Install the [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) in VS Code
2. Open `main.tex` in VS Code
3. The PDF auto-compiles on save — view it in the built-in PDF viewer

Full documentation: https://github.com/James-Yu/LaTeX-Workshop/wiki

#### First-time setup

LaTeX Workshop requires a LaTeX distribution (see Prerequisites). Once installed:

- Open VS Code settings (`Cmd+,` / `Ctrl+,`)
- Search for `latex-workshop.latex.tools` to verify the recipe chain
- Default recipe uses `latexmk` with `pdflatex` — no extra config needed for this template

#### Build manually in VS Code

Open the command palette (`Cmd+Shift+P` / `Ctrl+Shift+P`) and run:

```
LaTeX Workshop: Build with recipe
```

Select **`latexmk (latexmkrc)`** or **`pdflatex`**.

#### View the PDF in VS Code

```
LaTeX Workshop: View LaTeX PDF
```

Or press the preview button (top-right of the editor when `main.tex` is open).

---

### Option 2: Command Line

```bash
pdflatex main.tex
```

Or with latexmk for automatic dependency resolution:

```bash
latexmk -pdf main.tex
```

Clean build artifacts:

```bash
latexmk -c
```

---

## Font Options

The template defaults to the standard LaTeX font. Uncomment one of these lines in `main.tex` to switch:

```latex
% sans-serif
\usepackage[sfdefault]{FiraSans}
\usepackage[sfdefault]{roboto}
\usepackage[sfdefault]{noto-sans}
\usepackage[default]{sourcesanspro}

% serif
\usepackage{CormorantGaramond}
\usepackage{charter}
```

Ensure the corresponding font package is installed in your LaTeX distribution.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `File not found` errors | Run `tlmgr install <package>` (macOS/Linux) or use MiKTeX Package Manager (Windows) |
| PDF not updating | Delete `.aux`, `.log`, `.out` files and rebuild |
| Content overflows one page | Reduce font size in `\documentclass[letterpaper,11pt]` to `10pt` or trim bullet points |
| LaTeX Workshop not building | Confirm `latexmk` is on your PATH: `which latexmk` |
