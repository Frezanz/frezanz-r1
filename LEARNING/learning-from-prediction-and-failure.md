# Learning from Prediction and Failure

## Goal

Investigate learning processes that improve reusable reasoning paths, formula selection, representations, and structural choices—not only next-token prediction.

## Proposed loop

1. Generate one or more predictions or candidate paths.
2. Execute or test candidates where possible.
3. Compare outputs against evidence, task constraints, or a trusted evaluator.
4. Classify failure: missing information, incorrect assumption, wrong formula, representation gap, routing error, search limitation, or evaluator uncertainty.
5. Change the component implicated by the evidence.
6. Test the change on new cases and regression cases.
7. Keep it only if the measured trade-off is better.

## Important distinction

A lower training loss or a plausible answer is not enough to show improved intelligence. Use held-out tasks, controlled baselines, calibrated uncertainty, and resource measurements. For open-ended tasks, evaluation may be uncertain and human feedback may be needed.

## Research metrics

- sample efficiency;
- held-out task success and transfer;
- correction and recurrence rate for each error class;
- calibration and appropriate abstention;
- compute/latency per successful task;
- regression rate after adaptation;
- usefulness and reusability of learned paths.

## Status

Proposed direction. Requires a prototype and controlled tests before conclusions can be drawn.
