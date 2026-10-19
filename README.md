# Performance Direction Assessment

A minimalist, gamified self-assessment that shows a person where to focus before a discovery call. One static page, no build step, no server, no dependencies.

**What it does**

- 5 stages (Direction, Awareness, Regulation, Choice, Consistency), 4 statements each
- Stage rail and a short "stage complete" moment between stages
- Readiness check and four optional reflection prompts
- Results: total score, domain bars, two priorities, a strength, and one question to bring to the call
- Copy result and Save as PDF (print) buttons
- Progress saves in the visitor's browser, so a refresh does not lose answers
- Answers never leave the visitor's device

## Customise

Open `index.html` and edit the `CONFIG` block near the top of the script:

```js
var CONFIG = {
  brand: "",            // small name shown top-left
  bookingUrl: "",       // your booking link; leave empty to hide the button
  bookingLabel: "Book your free discovery call"
};
```

Colours are the CSS variables at the top of the file (`--accent` is the main one).

## Test locally

Open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000.

## Publish with GitHub Pages

1. Create a new public repository on GitHub, for example `direction-assessment`.
2. Add `index.html` and `README.md` to it. Upload through the web page, or from a terminal:
   ```
   git init
   git add .
   git commit -m "Add assessment"
   git branch -M main
   git remote add origin https://github.com/<your-username>/direction-assessment.git
   git push -u origin main
   ```
3. In the repository, go to Settings, then Pages. Under "Build and deployment", set Source to "Deploy from a branch", choose `main` and `/ (root)`, and save.
4. After a minute or two the site is live at `https://<your-username>.github.io/direction-assessment/`.

## Notes

- This is a self-reflection tool, not a clinical or psychometric test, and the page says so.
- There is no backend, so you do not receive responses. To collect them, add a form service (for example Formspree or Google Forms) later; ask if you want that built in.
- Scoring follows the Pre-Discovery Assessment doc: domain bands 4 to 9 / 10 to 14 / 15 to 20, Direction always ranks first when it is 4 to 9, ties break in the order Direction, Awareness, Regulation, Choice, Consistency.
