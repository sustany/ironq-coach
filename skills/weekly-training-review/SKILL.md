---
name: weekly-training-review
description: Review the athlete's last week of training from their IronQ log against the week before. Use when someone asks how their training went this week, for a weekly check-in or Sunday review, whether they did enough, or what to change next week.
---

# Weekly training review

Read the athlete's own IronQ log and give a short, honest review of the last 7 days against the 7 days before, ending with one change for next week.

## Steps

1. Call `get_training_summary` with `weeks: 3`. If it says the person must sign in, tell them in one line that Claude needs them to connect IronQ, then stop and wait.
2. Call `list_workouts` with `from` set to 14 days ago, to see which days they trained and what each workout was.
3. Call `get_body_change` with `weeks: 4`. Skip the body-weight part of the review if it returns no weigh-ins.
4. Call `get_personal_records` and pick out any record set in the last 7 days.
5. If one workout stands out (much lower volume, a missed day, a record), call `get_workout` for that date to see why.

## What to write

- One sentence verdict first: better, about the same, or worse than last week, and the main reason.
- A small table, this week next to last week: workouts, working sets, volume (lb), cardio minutes, average body weight.
- Up to three short points: what went well, what slipped, any new record.
- **One change for next week**, specific and doable (for example "add one working set to back on Tuesday", not "train harder").

## How to read IronQ numbers

- Weights are pounds as logged on the machine. A plate-loaded machine logged as ONE SIDE is one side, so never double it or compare it with a two-sided number.
- Warm-up sets are flagged and already left out of volume and records. Never count them.
- `e1rm_lb` is an estimated one-rep max from working sets of 12 reps or fewer. Call it an estimate.
- Calories and fat burned in workouts are estimates, not measurements, and fat burned is not net fat loss. Say so if you use them.
- Judge body weight by the weekly average, never by one weigh-in. A change of under 1 lb in a week is noise unless it continues.
- If `get_profile` shows the last sync was days ago, say the log may be missing recent workouts.

Do not give medical advice. If a drop in training looks like illness or injury, say so plainly and suggest they get it checked rather than pushing through.
