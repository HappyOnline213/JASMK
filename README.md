# JASKM — Journal of Applied Social Mechanics & Interpersonal Kinematics

Website for the W-R-Y Phenomenon research paper series.

---

## File Structure

```
jaskm-site/
├── index.html        ← The website (never needs editing)
├── papers.json       ← List of paper filenames (edit this when adding a paper)
├── papers/
│   ├── paper1.html   ← Paper I  (W-R-Y Phenomenon)
│   ├── paper2.html   ← Paper II (Factorized Correction Model)
│   ├── paper3.html   ← Paper III (Origin Mechanics & PID)
│   └── paper4.html   ← Paper IV (H-O Standard Model)
└── README.md         ← You are here
```

---

## How to Add a New Paper

### Step 1: Create the paper file

Create a new file in the `papers/` folder, e.g. `paper5.html`.

The file has two parts separated by a `META-->` tag:
- **Top part:** metadata in JSON inside `<!--META ... META-->` comment
- **Bottom part:** the article body in plain HTML

Example template:

```html
<!--META
{
  "id": "paper5",
  "vol": 1,
  "issue": 5,
  "type": "Research Article",
  "title": "Your Paper Title Here",
  "authors": "Ng Yong Jie, Mark Hui Qin, Chloe Lau",
  "affiliation": "Applied Behavioral Research Division, McDonald's, Melaka, Malaysia",
  "doi": "10.XXXX/jaskm.2026.0005",
  "submitted": "10 June 2026",
  "accepted": "12 June 2026",
  "published": "13 June 2026",
  "keywords": ["keyword one","keyword two"],
  "abstract": "Your abstract here. Use plain text, no line breaks."
}
META-->

<h2>1. Introduction</h2>
<p>Your paper body here. Just normal HTML.</p>

<h3>1.1 Subsection</h3>
<p>More text...</p>

<div class="equation">Your equation here</div>

<table>
<tr><th>Header</th><th>Header</th></tr>
<tr><td>Data</td><td>Data</td></tr>
</table>

<div class="footnote">
<p>Corresponding author: Ng Yong Jie (applied.behavioral.research@mcdonalds.edu.my).</p>
</div>
```

### Step 2: Add the filename to papers.json

Open `papers.json` and add your new filename at the **top** of the list (newest first):

```json
[
  "paper5.html",
  "paper4.html",
  "paper3.html",
  "paper2.html",
  "paper1.html"
]
```

That's it. The website picks it up automatically.

### HTML Tags Cheat Sheet

| What you want          | HTML to use                                    |
|------------------------|------------------------------------------------|
| Main section heading   | `<h2>1. Title</h2>`                           |
| Subsection heading     | `<h3>1.1 Subtitle</h3>`                       |
| Paragraph              | `<p>Text here</p>`                            |
| Bold text              | `<strong>bold</strong>`                        |
| Italic text            | `<em>italic</em>`                              |
| Subscript (e.g. S₁)   | `S<sub>1</sub>`                                |
| Centered equation      | `<div class="equation">W-R-Y = κ × (α ⊗ β) × γ</div>` |
| Table                  | See example above                              |
| References section     | Wrap in `<div class="references">...</div>`   |
| Footnote/author line   | Wrap in `<div class="footnote">...</div>`     |

---

## How to Deploy (Free)

### Option A: GitHub Pages (Recommended)

1. Create a GitHub account if you don't have one
2. Create a new repository (e.g. `jaskm-journal`)
3. Upload all files from this folder, keeping the folder structure
4. Go to **Settings → Pages → Source**: select `main` branch, `/ (root)`
5. Your site will be live at `https://yourusername.github.io/jaskm-journal/`

To add papers later: upload the new `.html` file to the `papers/` folder and update `papers.json` directly on GitHub.

### Option B: Netlify

1. Go to https://app.netlify.com/drop
2. Drag the entire `jaskm-site` folder onto the page
3. Done — instant URL

---

## Local Testing

Because the site loads paper files via `fetch()`, opening `index.html` directly in a browser won't work (browsers block local file fetches). Use a local server:

```bash
# Python (if installed)
cd jaskm-site
python3 -m http.server 8000
# Then open http://localhost:8000

# Or Node.js
npx serve .

# Or VS Code: install "Live Server" extension, right-click index.html → Open with Live Server
```

---

## Disclaimer

This is a satirical, non-commercial project for entertainment purposes only.
Not affiliated with McDonald's Corporation or any academic institution.
