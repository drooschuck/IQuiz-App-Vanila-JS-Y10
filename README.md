 # IQuiz — Year 10 Quiz App

 Small single-page, static quiz app (Year 10 / KS4). Questions are stored as ES modules under the `data/` folder and dynamically imported by `js/script.js`.

 Live demo: https://ks4-y10.onrender.com

 ---

 ## Features

 - Single-page quiz UI in `index.html` (loads `js/script.js` as an ES module)
 - Subjects selection (Science / Math / CS / English)
 - Questions are dynamically imported from `data/<subject>/...` files so you can add dated question modules
 - Per-question timer and scoring

 ## Quick start — run locally

 The app uses ES module imports, so it must be served over HTTP (opening the file with `file://` will fail).

 Recommended quick options (run from the project root):

 - Python 3 (works on Windows/macOS/Linux):

 ```bash
 # from repository root (Windows cmd / PowerShell)
 python -m http.server 8000

 # then open in your browser:
 http://localhost:8000/index.html
 ```

 - Node (npx http-server):

 ```bash
 npx http-server -p 8000
 http://localhost:8000/index.html
 ```

 - Or use VS Code Live Server extension to serve the workspace folder.

 ## Project structure (important files)

 - `index.html` — application entry page
 - `style.css` — styling
 - `js/script.js` — main app logic (loads question modules, shows quiz UI)
 - `data/` — question modules grouped by subject and date (e.g. `Y9_Math_YYYY-MM-DD.js`)

 Example question module must export at least `questions` (array) and may export `quizSubject`:

 ```js
 // example: data/math/Y9_Math_2025-12-01.js
 export const quizSubject = 'Maths — Algebra';
 export const questions = [ {numb: 1, question: 'Q text', options: ['a','b','c','d'], answer: 'a'} ];
 ```

 ## Notes / Troubleshooting

 - If the console shows a module loading error, confirm you used a static server and the data file exists with the expected filename format (the app dynamically imports by date and subject).
 - The default behaviour looks for a data file named like `Y9_Math_YYYY-MM-DD.js` (today's date by default) — provide an available date in the `data/` tree or change the `script.js` loader call.

 ## Contributing

 Add new subject/date modules to `data/` using the existing filename pattern and export shape (see above). Keep questions in the `questions` array.

 ## Author

 Droos Chuck

 ---

 (Generated README to make running and contributing easier.)
