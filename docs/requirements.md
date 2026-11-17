# Phase 1 — Requirements

**Status:** draft · **Last updated:** 2026-11-17

> Items marked **[PK]** are engineering work you have to do yourself. Everything else is structure.

## 1. Why the previous frame failed

- **Structural:** the frame was printed in PLA lying flat, so the layer lines ran across the load path at the arm-to-hub joints. Under load, the frame split along those layer boundaries, which are the weakest direction in a printed part.
- **Joints:** the arms were held by friction fits and screws driven straight into plastic. Neither gives a repeatable clamping load, and both loosen under vibration.
- **Mounting:** the battery and the Pixhawk weren't positively retained, and the battery could shift at some attitudes. That moves the center of gravity in flight.
- **Radio:** the RadioMaster Pocket (ELRS) never bound to the R88 receiver. The R88 only speaks FrSky D8/D16 and Futaba SFHSS, so the two were never compatible. This was not a configuration error. Fix: an ELRS receiver connected to the Pixhawk over serial (CRSF).
- **[PK] Open question:** at the arm root, was the failure driven by bending stress or shear? Answer this after the Phase 2 teaching block, then come back and update this line.

## 2. Mass budget

Catalog values are what the seller lists. Measured values come from your kitchen scale. The gap between the two columns is your first predicted-vs-measured comparison.

| Component | Qty | Catalog each (g) | Catalog total (g) | Measured total (g) **[PK]** | Catalog source / note |
|---|---|---|---|---|---|
| EMAX ECO II 2807 1500KV motor | 3 | 46.9 | 140.7 | | Seller spec, without wires |
| Hobbywing XRotor 40A ESC | 3 | 26 | 78 | | Basic (non-PRO) version; confirm yours isn't a PRO (~45 g) |
| MG90S servo | 1 | 13.4 | 13.4 | | Not verified against a source; weigh it |
| RadioMaster R88 receiver | 1 | 11 | 11 | | Seller spec. Being replaced by an ELRS receiver |
| Pixhawk 2.4.8 | 1 | ~36 | ~36 | | Radiolink listing (1.28 oz). Clones vary; weigh it |
| Matek PDB | 1 | — | — | | Model unknown; weigh it |
| Ovonic 4S 2200 mAh 50C | 1 | — | — | | No reliable listing for the 50C version; weigh it |
| Ovonic 3S 1300 mAh 50C | 1 | 114 | 114 | | Seller spec, EC3 version, ±20 g |
| Props (size TBD) | 3 | — | — | | Set after prop selection |
| Wiring, connectors, hardware | — | — | — | | Estimate later; weigh during build |
| **Frame (new design)** | 1 | — | — | | Output of Phase 2 CAD |
| **Total, without battery** | | | | | |
| **All-up weight (with chosen battery)** | | | | | |

## 3. Requirements

**How to write one:** "The airframe **shall** [do something] [measurable value]." Every requirement needs a number, a reason, and a way to prove you met it. The four verification methods are **Test, Analysis, Inspection, Demonstration**. If you can't name the method, the requirement isn't finished yet.

| ID | Requirement **[PK]** | Target **[PK]** | Rationale **[PK]** | Verification **[PK]** |
|---|---|---|---|---|
| R-01 | All-up weight | | | |
| R-02 | Thrust-to-weight ratio | | | |
| R-03 | Hover endurance | | | |
| R-04 | Arm-joint strength / stiffness | | | |
| R-05 | Battery and avionics retention | | | |

Starting points for R-01 to R-03 are in the session notes: the mass table feeds weight, the motor thrust data feeds T/W, and the battery choice plus estimated hover current feeds endurance.

## 4. Predictions (written before Phase 3)

A prediction is a number written down *before* testing that the test can prove wrong. Design choices like "print at an angle" or "use threaded inserts" aren't predictions. A prediction says what those choices will achieve, in numbers.

| ID | Prediction **[PK]** | Method | Test that checks it |
|---|---|---|---|
| P-01 | | Hand calc (Phase 2) | |
| P-02 | | FEA (Phase 2) | |

## 5. Open risks

| Risk | Status |
|---|---|
| Radio link has never worked | Cause identified (protocol mismatch). Needs an ELRS receiver; confirm the Pocket's firmware version first |
| No flight baseline exists | Open |
| One LiPo has an unidentified charging issue | Open; identify which pack before any flight |
| Tail yaw mechanism adds 1–2 weeks across Phases 2–4 | Accepted |
| Winter: indoor or cold-weather flight test plan needed | Open |
