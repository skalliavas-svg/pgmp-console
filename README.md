# PgMP Study Console

A single-file, self-contained study tool for the PMI **Program Management Professional (PgMP)** exam. Open `pgmp-console.html` in any browser — no build step, no server, no dependencies.

## What it does

- **Quiz engine** with four question types: single-select, multi-select, scenario/case (with sub-questions), and matching.
- **500-question bank** spanning all five domains of PMI's PgMP Examination Content Outline (ECO), weighted toward each domain's real exam proportion:

  | Domain | Blocks | Questions |
  |---|---|---|
  | Strategic Program Management | ST1–ST8 | 100 |
  | Life Cycle Management | LC1–LC11 | 100 |
  | Benefits Management | BN1–BN9 | 100 |
  | Stakeholder Engagement | SH1–SH10 | 100 |
  | Governance | GV1–GV10 | 100 |

  48 topic blocks total. Questions are hard, scenario-based judgment calls rather than simple recall — each has one clearly correct answer with plausible distractors.
- **Randomized sessions**: each block practice session samples a subset of its question pool (up to 10 questions) rather than showing every question every time. A **"⟳ New Set"** button reshuffles the draw without leaving the block.
- **Flashcards** with Leitner-box spaced repetition (5 boxes, increasing review intervals).
- **Multiple session modes**: block practice, a quick domain-mixed exam, a timed full-length mock exam, and a focus drill that targets your weakest tags.
- **Progress persistence** via `localStorage` — mastered blocks, per-tag performance stats, exam history, and flashcard review state all survive a page reload.
- **Domain-weighted scoring and proficiency bands** (Above Target / Target / Below Target / Needs Improvement) so you can see where to focus.

## Using it

1. Open `pgmp-console.html` in a browser (double-click the file, or serve it with any static file server).
2. Work through topic blocks to unlock the quick exam and, once you've seen enough questions twice, the focus drill.
3. Use the timed mock exam to simulate real exam pacing.
4. Use flashcards for terminology and quick-recall review alongside the scenario questions.
5. Progress is saved locally in your browser. Use the reset option on the dashboard to clear it and start over.

## Content sources

Question content is original material written to test judgment and application of PgMP concepts, informed by:

- PMI PgMP Examination Content Outline (ECO)
- PMI PgMP Handbook
- *The Standard for Program Management*, 5th edition (concepts only — no copyrighted text is reproduced)
- PMI Code of Ethics and Professional Conduct

## Project structure

Everything lives in one file:

```
pgmp-console.html
├── <style>   theme (light/dark via CSS custom properties), component styles
└── <script>  data (DOMAINS, REFS, BLOCKS, FLASHCARDS) + app logic
    (vanilla JS, no framework, single `state` object, template-string rendering)
```

There is no build process — edit the HTML file directly and open it in a browser to see changes.
