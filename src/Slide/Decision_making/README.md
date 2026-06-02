# Python Basics & Syntax — Modular Slidev Project

## Project Structure

```
slidev-project/
├── main.md              ← Entry point — imports all slide files via <src>
├── main.css             ← Shared global stylesheet (design system)
├── setup/
│   └── main.ts          ← Loads main.css globally for all slides
├── slide1.md
├── slide2.md
├── slide3.md
├── slide4.md
├── slide5.md
├── slide6.md
├── slide7.md
├── slide8.md
├── slide9.md
├── slide10.md
├── slide11.md
├── slide12.md
├── slide13.md
├── slide14.md
├── slide15.md
├── slide16.md
├── slide17.md
├── slide18.md
├── slide19.md
├── slide20.md
├── slide21.md
├── slide22.md
├── slide23.md
├── slide24.md
├── slide25.md
├── slide26.md
├── slide27.md
└── README.md
```

## Running the presentation

```bash
npm install -g @slidev/cli
slidev main.md
```

## How CSS is shared

`main.css` contains the full design system (CSS variables, layout helpers, cards,
callouts, tables, typography, flowchart nodes, memory boxes, etc.).
It is imported once in `setup/main.ts`, which Slidev automatically picks up,
making all classes available in every slide with no duplication.
