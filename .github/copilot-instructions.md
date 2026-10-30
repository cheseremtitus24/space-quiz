# Copilot instructions

## Project shape

- The quiz is a self-contained browser app in `index.html`: markup, CSS, quiz data, and vanilla JavaScript live together. There is no framework, package manager, server requirement, or external runtime dependency; open the file directly in a browser.
- The question array is the source of truth for quiz length and content. `renderQuestion()` draws the current question and progress, `selectAnswer()` handles one answer and updates score and feedback, and `showResults()` replaces the card with the final result and replay action.
- Styling is based on CSS custom properties, with a `prefers-color-scheme` dark palette and reduced-motion handling. Keep UI updates consistent with those theme and accessibility behaviors.

## Conventions

- Each question uses `{ q, a, correct, fact }`; `correct` is a zero-based index into `a`. Keep answer choices and the correct index aligned. Derive counts from `questions.length` rather than hard-coding the quiz length.
- Keep quiz state (`current`, `score`, `answered`) in the existing script and use the existing render/answer/results flow when changing quiz behavior.
- Preserve the single-file, dependency-free design. Put page styles in the existing `<style>` block and app logic/data in the existing inline `<script>`.
- Use semantic buttons and live announcements for answer feedback; preserve keyboard focus styling and `prefers-reduced-motion` support when adjusting interactions.

## Build and verification

- No build, test, or lint commands are configured. For a browser smoke test, open `index.html`, complete all questions, check scoring/progress and the results screen, then try replay. Check both color schemes and reduced-motion behavior when changing presentation or animation.
