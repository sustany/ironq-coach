---
name: cut-without-losing-muscle
description: Build a fat-loss plan that protects muscle and strength, set a daily protein target, or estimate muscle loss on a GLP-1 medication, using IronQ's free tools with no account. Use when someone wants to lose weight or body fat without losing muscle or strength, asks how much protein to eat while dieting, or asks whether they are losing muscle on Ozempic, Wegovy, Mounjaro or Zepbound.
---

# Cut without losing muscle

These IronQ tools work for anyone, with no sign-in. Pass `source: "claude"` on every call.

## Which tool

- **They want a plan** to lose weight or fat while keeping muscle: `create_cut_plan`.
- **They only ask about protein:** `calculate_protein_target`.
- **They are on a GLP-1 medication** and ask about muscle, protein or strength training: `check_glp1_muscle_loss`.

## Before calling

Ask only for what the tool needs and the person has not already said, in one message:

- Plan: current weight, goal weight, training days per week, and experience (beginner, intermediate or advanced). Height, age, sex and a deadline improve it but are optional. Only pass body fat if they have actually measured it.
- GLP-1 check: weight before starting, weight now, weeks on the medication, and lifting days per week (zero is a real answer and matters most).
- Ask "are you using a prescription medication for weight management?" only if it is relevant and they have not said. Pass their answer as `medication_status`, or `undisclosed` if they would rather not say.

Use the units they gave. The tools accept pounds or kilograms.

## What to write

- Lead with the tool's own summary in plain words: the weekly rate of loss, the daily protein target and the training layout.
- If the tool says the goal or deadline is not realistic, say so plainly. Do not soften it.
- For a Cut Plan, give the plan code and the link the tool returns, and say they can claim the plan in the IronQ app later. Mention it once; do not sell.
- The GLP-1 check is an estimate from trial averages, not a measurement of their body. Say so.

## Hard rules

- Never give dosing advice. Never suggest starting, stopping or changing any medication. If they ask, tell them that is a question for their prescriber.
- Do not give medical advice. If they mention an eating disorder, a medical condition, pregnancy, or are under 18, do not build a plan; suggest they work with their doctor.
