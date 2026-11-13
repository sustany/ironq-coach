---
name: next-session-prep
description: Suggest weights and reps for the athlete's next workout from their last IronQ sessions. Use when someone asks what weight to use today, what to lift next, how to progress an exercise, or to plan their next gym session.
---

# Next session prep

Give a short list of exercises with a suggested weight and rep target for each, based on how the same exercises went last time.

## Steps

1. Call `get_profile` for their current working weights and gyms.
2. Call `list_workouts` with `limit: 10`. If they named the session ("push day", "legs"), find the last workout of that type. Otherwise use the type they did least recently.
3. Call `get_workout` for that date to get every set: weight, reps, reps in reserve and the result against target.
4. For any exercise where the last session alone is unclear, call `get_exercise_history` for its last three sessions.

## How to choose the weight

For each exercise, look at its working sets last time:

- **Every working set hit the target reps with 2 or more reps in reserve:** go up by the smallest step the machine allows, usually 5 lb on upper-body work and 5 to 10 lb on lower-body work.
- **Hit the target reps but close to failure (0 or 1 in reserve):** same weight, aim for one more rep on the first set.
- **Missed the target reps once:** same weight.
- **Missed the target on two sessions in a row:** drop about 10 percent and build back.
- Plate-loaded machines logged as ONE SIDE stay ONE SIDE in your suggestion. Say "per side".

## What to write

A table: exercise, last time (weight x reps), today (weight x reps), and a few words of why. Then one line on anything to watch (for example "your last two chest sessions were short; keep rest under 2 minutes").

These are suggestions, not instructions. If the person says something hurts, do not suggest pushing through it; suggest a lighter weight or a different exercise, and getting pain checked if it persists.
