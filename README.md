# NIELIT CCC Practice Exam

A lightweight, bilingual Hindi–English practice website for candidates preparing for the NIELIT Course on Computer Concepts (CCC). It runs as a static site and loads questions from `questions.json`.

## Practice options

### Full Mock Test

- 100 randomly selected questions
- 90-minute timer
- 1 mark per correct answer, no negative marking
- Pass mark: 50
- Question navigation, answer status, and attempt saving in browser local storage
- Results and answer review after submission

### Chapter-wise Practice

- Choose a category from the categories present in `questions.json`
- Choose 10, 20, 30, or 50 questions
- **Learning mode:** check each answer and see immediate feedback
- **Exam mode:** answer the session first, then view the score and review answers

Questions show Hindi and English text together.

## Run locally

The site uses `fetch()` to load the JSON question bank, so open it through a local web server rather than opening `index.html` directly as a file.

With Python installed, run this from the project directory:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000](http://localhost:8000) in a browser.

## Deploy with GitHub Pages

1. Push or merge the site files to the branch and folder configured in the repository's **Settings → Pages**.
2. Wait for the Pages deployment workflow to finish.
3. Open the published URL and try both the mock test and chapter practice.

A deployment is not triggered by this README itself unless the repository's Pages source includes the branch being updated.

## Project files

- `index.html` — page structure and screens
- `style.css` — responsive layout and visual styling
- `script.js` — question loading, session flow, scoring, results, and saved mock progress
- `questions.json` — bilingual question bank with category labels
- `assets/` — logo and interface icons

## Question bank format

Each question contains an ID, category, bilingual prompt, bilingual answer options, and the correct option key:

```json
{
  "id": 1,
  "category": "Computer Fundamentals",
  "question_hi": "प्रश्न हिंदी में",
  "question_en": "Question in English",
  "options": {
    "A": { "hi": "विकल्प", "en": "Option" },
    "B": { "hi": "विकल्प", "en": "Option" },
    "C": { "hi": "विकल्प", "en": "Option" },
    "D": { "hi": "विकल्प", "en": "Option" }
  },
  "correct": "A"
}
```

Use one of `A`, `B`, `C`, or `D` for `correct`. Questions with a missing category will not appear in chapter selection.
