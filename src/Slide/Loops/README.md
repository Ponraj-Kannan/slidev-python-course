# Python Looping Statements — Modular Slidev Project

## Project Structure

```
slidev-project/
├── main.md              ← Entry point — imports all slide files
├── main.css             ← Shared global stylesheet (design system)
├── setup/
│   └── main.ts          ← Slidev setup file — loads main.css globally
├── slide1.md            ← Global frontmatter + Slide 3: Introduction to Loops
├── slide2.md            ← Slide 4: While Loop — Syntax & Flow
├── slide3.md            ← Slide 5: While Loop — Tracing
├── slide4.md            ← Practice: While Loop (odd numbers)
├── slide5.md            ← Practice: While Loop (divide by 9)
├── slide6.md            ← Slide 7: For Loop — Syntax & String Iteration
├── slide7.md            ← Practice: For Loop (vowels)
├── slide8.md            ← Slide 8: For Loop — Lists & range()
├── slide9.md            ← Slide 9: range() — start, stop, step
├── slide10.md           ← Practice: For Loop (multiplication table)
├── slide11.md           ← Practice: For Loop (sum of evens)
├── slide12.md           ← Slide 10: while vs for Comparison
├── slide13.md           ← Slide 12: Nested Loops — Syntax & Execution
├── slide14.md           ← Practice: Nested Loops (number grid)
├── slide15.md           ← Practice: Nested Loops (number triangle)
├── slide16.md           ← Slide 14: break & continue Statements
├── slide17.md           ← Practice: Loop Control (break)
├── slide18.md           ← Slide 15: pass Statement & Comparison
├── slide19.md           ← Practice: Loop Control (star pattern)
├── slide20.md           ← Slide 16: else with Loops
└── slide21.md           ← Practice: else with Loops
```

## How CSS is shared

`main.css` contains the full design system (CSS variables, layout helpers, cards,
callouts, tables, typography). It is imported in `setup/main.ts`, which Slidev
automatically picks up — making all classes available in every slide file with
no duplication.

## Running the presentation

```bash
npm install -g @slidev/cli
slidev main.md
```
