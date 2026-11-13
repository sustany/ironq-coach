---
name: weight-plateau-check
description: Work out whether a weight-loss stall is a real plateau and what most likely causes it, from dated weigh-ins, using IronQ's free plateau check. Use when someone says their weight has stopped going down, the scale is stuck, they have hit a plateau, or they are not losing weight any more.
---

# Weight plateau check

Find out whether the stall is real before explaining it. Pass `source: "claude"` on every call.

## Steps

1. Get dated weigh-ins. If the person has connected IronQ, call `get_body_weight` for the last 6 weeks and use those. Otherwise ask them for four or more dated weigh-ins; four or more lets the trend be measured instead of assumed.
2. Ask, in one message, for whatever they know of: total weight lost so far, protein per day, daily steps, sleep hours, training days per week, and whether their lifts have gone up, stayed flat or gone down. All are optional; do not hold the answer back waiting for them.
3. If they have connected IronQ and you do not know the strength trend, call `get_training_summary` with `weeks: 6` and judge it from working sets and volume.
4. Call `analyze_weight_loss_plateau` with everything you have.

## What to write

- First line: is it a real plateau or not, and the measured weekly trend (for example "Not a plateau: you are still losing about 0.4 lb a week, the daily swings hide it").
- Then the ranked likely causes the tool returns, each with its check, in a short list.
- End with the tool's one recommended next step. Do not add a second.
- If lifts are going down, say that this changes the answer: the priority becomes keeping muscle, not losing faster.

Never recommend cutting calories further in response to a single weigh-in. Never give medication or dosing advice.
