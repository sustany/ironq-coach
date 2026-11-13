---
name: strength-progress
description: Tell the athlete whether they are still getting stronger on a lift, using their IronQ exercise history, and whether strength is holding while they lose weight. Use when someone asks if they are progressing, stuck, losing strength, or keeping muscle on a diet, on any exercise or overall.
---

# Strength progress

Answer one question with evidence: is this person getting stronger, holding, or slipping?

## Steps

1. If they named an exercise, call `list_exercises` to find the exact name, then `get_exercise_history` for it over the last 12 weeks. If several exercises match, ask which one, listing the matches.
2. If they asked about strength overall, call `get_personal_records`, pick their 3 to 5 most-trained exercises by working sets, and run `get_exercise_history` on each.
3. If they are losing weight or ask about keeping muscle, also call `get_body_change` with `weeks: 12`.

## How to judge

- Compare the best estimated one-rep max (`e1rm_lb`) of the first three sessions in the window with the last three. Use the top working set when there is no estimate.
- Within plus or minus 2.5 percent: **holding**. More than 2.5 percent up: **getting stronger**. More than 2.5 percent down across at least three sessions: **slipping**.
- Fewer than four sessions of that exercise: say there is not enough data yet and how many more sessions would settle it.
- Strength holding while the weekly average weight falls is a good sign that muscle is being kept. Strength falling while weight falls fast is the warning sign: say so plainly and suggest more protein, a slower rate of loss, or fewer hard sets per week, in that order.
- Never compare a ONE SIDE plate-machine number with a two-sided one, and never count warm-up sets.

## What to write

- The verdict first, in one line per exercise: getting stronger, holding, or slipping, with the numbers (for example "Leg press: 410 to 432 lb estimated max, up 5 percent in 8 weeks").
- A short table if more than one exercise.
- One next step. If they are slipping, give the most likely cause from the data (missed sessions, falling volume, fast weight loss) rather than a guess.

The estimated max is an estimate from reps, not a tested lift. Say so once.
