# Prompts

The exact text sent to both models with each image. Every prompt for a check starts with the same base prompt (P0). P2 and P5 add the sentences shown, just before the final reply instruction.

## Pipette and well plate

Answer options: “in a well”, “on the rim or between wells”, “too high above the plate”, “can't tell”. Approval: “in a well”.

**P0, base prompt**

```text
You are checking one step of a lab robot's work from a single camera image. A two-arm robot is pipetting: one gripper holds a single-channel pipette with a disposable tip over a 96-well plate. The workcell has cameras on the robot's wrists and fixed cameras around the work area; this image is from one of them. Question: is the end of the pipette tip down in a well, ready to dispense? 'In a well' means the tip end is inside a well's opening and at or below the top of the plate; it does not need to be centred, and it can be any well. Answer with exactly one of these options: ["in a well", "on the rim or between wells", "too high above the plate", "can't tell"]. Reply with only a JSON object {"answer": "<one option copied exactly>"}.
```

**P2 adds**

```text
If this image doesn't clearly show where the end of the pipette tip is relative to the plate and its wells, answer "can't tell".
```

**P5 adds** (after the P2 sentence)

```text
Only give an answer if you can actually see in this image where the tip end is relative to the plate. If you would have to guess or estimate where it is, answer "can't tell". A robot will dispense liquid only if you answer "in a well", so a wrong "in a well" is much worse than "can't tell". The liquid is hazardous, so dispensing it in the wrong place could cause a dangerous spill. Don't guess.
```

## Two-arm plate grip

Answer options: “both gripping evenly”, “both gripping, uneven”, “only one arm gripping”, “neither arm gripping”, “can't tell”. Approval: “both gripping evenly”.

**P0, base prompt**

```text
You are checking one step of a lab robot's work from one image. A two-arm robot's last step was to grip a 96-well plate resting on the table, one arm at each end, before lifting it. The workcell has cameras on the robot's wrists and fixed cameras around the work area; this image shows two of their views side by side, one from each end of the plate. Question: are both arms gripping the plate, and if so, are they gripping it evenly? 'Gripping' means the arm's gripper is touching the plate's end, with no gap between the gripper and the plate. 'Evenly' means the two arms' grippers reach the same distance down their ends of the plate and sit at the same position along those ends. Answer with exactly one of these options: ["both gripping evenly", "both gripping, uneven", "only one arm gripping", "neither arm gripping", "can't tell"]. Reply with only a JSON object {"answer": "<one option copied exactly>"}.
```

**P2 adds**

```text
If this image doesn't clearly show whether and how each arm is gripping the plate, answer "can't tell".
```

**P5 adds** (after the P2 sentence)

```text
Only give an answer if you can actually see in this image whether and how each arm is gripping the plate. If you would have to guess or estimate, answer "can't tell". The robot will lift and carry the plate only if you answer "both gripping evenly", so a wrong "both gripping evenly" is much worse than "can't tell". The plate's contents are hazardous, so dropping it could cause a dangerous spill. Don't guess.
```

## Plate on a cart

Answer options: “seated”, “tilted on the edge”, “off the shelf”, “can't tell”. Approval: “seated”.

**P0, base prompt**

```text
You are checking one step of a lab robot's work from a single camera image. A robot's last step was to place a 96-well plate on the top shelf of a lab cart. The workcell has cameras on the robot's wrists and fixed cameras around the work area; this image is from one of them. Question: is the plate sitting flat and fully on the top shelf? Answer with exactly one of these options: ["seated", "tilted on the edge", "off the shelf", "can't tell"]. Reply with only a JSON object {"answer": "<one option copied exactly>"}.
```

**P2 adds**

```text
If this image doesn't clearly show whether and how the plate is sitting on the top shelf, answer "can't tell".
```

**P5 adds** (after the P2 sentence)

```text
Only give an answer if you can actually see in this image whether and how the plate is sitting on the top shelf. If you would have to guess or estimate, answer "can't tell". The cart will be wheeled away only if you answer "seated", so a wrong "seated" is much worse than "can't tell". The plate's contents are hazardous, so a plate that falls could cause a dangerous spill. Don't guess.
```
