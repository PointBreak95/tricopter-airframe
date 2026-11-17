# tricopter-airframe

A custom tricopter airframe, designed from requirements and validated by test. Every design decision follows the same loop: **requirement → prediction → test → measured result → decision.**

**Why it exists:** my first tricopter frame (3D-printed PLA) never flew. It split along print layer lines at the arm-to-hub joints, and the radio link never worked. I "tested" its flight by using workaround in ardupilot by wiring it to my computer which led to a crash and realization of the structural weak points. This project replaces it with a frame I can analyze, test, and defend with numbers. I have been making use of Claude AI to help me plan and log this project as I work through it.

**Current phase:** 1 — Requirements

## Status

| Phase | Deliverable | Status |
|---|---|---|
| 1. Requirements | [`docs/requirements.md`](docs/requirements.md) — targets, mass budget, why the old frame failed | In progress |
| 2. Design & analysis | CAD, hand calcs (arm stress, deflection, natural frequency), FEA, design review | Not started |
| 3. Fabrication | Build log, as-built mass vs. predicted | Not started |
| 4. Test | Thrust stand characterization, arm deflection test, flight logs (vibration FFT, PID tuning) | Not started |
| 5. Package | Final report: predicted vs. measured, conclusions | Not started |

## Repo layout

```
docs/        requirements, design review, test reports
build-log/   dated work-session notes
cad/         STEP exports at design milestones (added in Phase 2)
analysis/    hand calcs and FEA results (added in Phase 2)
test/        procedures and raw data (added in Phase 4)
```

## Hardware carried over from the first build

3x EMAX ECO II 2807 1500KV motors · 3x Hobbywing XRotor 40A ESCs · MG90S tail servo · Pixhawk 2.4.8 (ArduPilot) · Matek PDB · 4S 2200 mAh and 3S 1300 mAh LiPos. Full mass budget in [`docs/requirements.md`](docs/requirements.md).
