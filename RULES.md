# Study Rules

## The cycle
One pattern is studied for 6 days.

| Phase | When | What happens |
|-------|------|--------------|
| Learn | Day 0 | Pick a theme. Get the top 5 exercises with NeetCode videos and study them. |
| Practice | Days 1-5 | Solve 2 exercises per day (10 total) with that pattern. Each one is logged here. |
| Gate | After Day 5 | The repo is checked. Only if the rule below is met can a new pattern start. |

## Logging an exercise
Required: tag (pattern slug), exercise, Python solution, time complexity, memory complexity.
Optional: date (default today, America/Sao_Paulo), notes.
Each exercise gets its own folder with `solution.py` and `README.md`:

    patterns/<NN>-<pattern-slug>/<YYYY-MM-DD>_<lc-number>-<problem-slug>/

## The gate rule
To start a new pattern, within the 7 calendar days before the request the repo must show, for the current pattern:

- at least 5 distinct days,
- each with at least 2 exercises tagged with the current pattern,
- at least 10 exercises in total.

What does not count:

- The 5 Learn-mode study exercises (unless solved again on a practice day).
- Exercises tagged with a different pattern.
- The same LeetCode problem twice in one cycle.
- Extra exercises on one day do not cover a missing day (3 on Monday is not 2 on Monday plus 1 on Tuesday).

If the gate is closed, keep practicing the current pattern until any rolling 7-day window satisfies the rule.
The first cycle has no previous pattern, so the gate is open.
The only override is the explicit phrase `OVERRIDE GATE: <reason>`, which is recorded in `progress.json` and in the README log.

## Dates
All dates use the `America/Sao_Paulo` timezone.
