# SolarDes Test Stand — SCADA Training Simulator (v1.0)

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Role-Interactive_SOP_Trainer-emerald.svg)](#1-what-this-is-ushbu-loyiha-nima)

> **⚠️ ENGINEERING DISCLAIMER (MUHANDISLIK IZOHI):**
> **O‘quv vositasi. Fizik model va barcha SOP/scaling parametrlari illyustrativ (illustrative). Muhandislik qarorlari uchun ishlatilmaydi. Test Stand real o‘lchovlari bilan validatsiya qilinmagan.**
> *(Educational tool only. The thermodynamic & fouling models use illustrative parameters. Not for engineering design or sizing decisions. Not yet validated against physical Test Stand measurements.)*

## 1. What This Is (Ushbu loyiha nima?)

**SolarDes Test Stand — SCADA Training Simulator v1.0** is an interactive, browser-based **Standard Operating Procedure (SOP) & SCADA Procedure Trainer** for vacuum-assisted interfacial solar/Near-IR desalination test benches.

It is designed to train operators, students, and lab engineers on:
- **5-Stage SOP Execution:** Mechanical assembly & optical alignment ($\Delta T \le 8\%$), 16-channel sensor calibration, 24-hour vacuum leak testing ($\Delta P/\Delta t < 0.20\text{ kPa/h}$), clean water baseline ($h_0$) determination, and 30-day seawater operation.
- **Dynamic PASS Gate Enforcement:** Prevents operators from advancing to subsequent operational phases when prerequisite safety or quality gates fail.
- **Fault Propagation (`-999` Cascade) & Emergency Response:** Demonstrates how a single thermocouple disconnect (`T1 = -999`) invalidates downstream derived KPIs (`T_surf_avg -> NaN`, `h_eff -> NaN`, `System State -> WARNING`) and trains operators on `E-STOP` / `RESET` recovery.
- **First-Principles Thermodynamic Consistency:** Uses the Antoine equation and latent heat balance in real time rather than hardcoded static lookup arrays.

## 2. What This Is NOT (Ushbu loyiha nima EMAS?)

- ❌ **NOT a Digital Twin:** It is not coupled to live physical hardware and is not calibrated to a specific commercial plant.
- ❌ **NOT a Validated Engineering Model:** It must not be used for commercial equipment sizing, EPC guarantees, or construction sign-off.
- ❌ **NOT a Construction Specification:** Mechanical dimensions ($60\text{ L}$, $0.5\text{ m}^2$) and process thresholds shown in the UI represent an educational laboratory test stand setup.

## 3. Numbers Are Illustrative (Konfiguratsiyalanadigan Illyustrativ Raqamlar)

All fouling kinetics, back-flush schedules, chemical dosing concentrations, and SOP gate thresholds in `simulator.html` are centralized in the `CONFIG` block and marked as **illustrative**:

```javascript
// ⚠️ ILLUSTRATIVE VALUES — For training purposes only.
// Actual scaling kinetics, back-flush schedules, and chlorine dosing
// are proprietary and must be determined experimentally for each system.
const CONFIG = {
  SCALING_RATE_NORMAL: 0.0273,  // illustrative (typical range: 0.02–0.05 / day)
  SCALING_RATE_SEVERE: 0.038,   // illustrative
  FLUSH_INTERVAL_H: 6,          // illustrative (typical: 4–8 hours)
  FLUSH_DURATION_MIN: 5,        // illustrative (typical: 3–10 minutes)
  CHLORINE_DOSE_PPM: 0.4,       // illustrative (typical: 0.2–1.0 ppm)
  CRITICAL_THRESHOLD: 0.80      // illustrative industry practice (70–85% of h0)
};
```

## 4. Real Experimental Data Is Private (Yopiq Ma'lumotlar va NDA)

Experimental telemetry from physical test runs, optimized anti-scaling regimes, brine management hydraulics, dry-cooler geometry, and the full engineering passport are **proprietary and strictly private**. See [`docs/what-is-NOT-public.md`](docs/what-is-NOT-public.md) for details on what is excluded from this public repository and how institutional/EPC partners can request access under NDA.

## 5. Quick Start & Repository Structure

No build step or server is required. Open `simulator.html` directly in any modern browser.

```text
SolarDes-BT01-Simulator/
├── LICENSE                    ← Apache 2.0 full text (with Patent & Trademark clauses)
├── NOTICE                     ← Trademark and copyright attribution
├── README.md                  ← Overview, disclaimer, and boundaries
├── simulator.html             ← Self-contained v1.0 SCADA Training Simulator
├── docs/
│   ├── physics.md             ← Open thermodynamic equations (Antoine, latent heat, h_eff)
│   ├── sop-structure.md       ← 5-Stage SOP & 7-Gate educational framework
│   ├── disclaimer.md          ← Full legal and engineering disclaimer
│   └── what-is-NOT-public.md  ← Scope of proprietary IP kept outside this repository
└── CONTRIBUTING.md            ← Contribution policy (bug reports welcome; scope locked)
```

## 6. How to Contribute

Bug reports on thermodynamic formulas, UI responsiveness, or accessibility are welcome via GitHub Issues. Please read [`CONTRIBUTING.md`](CONTRIBUTING.md) before opening a pull request—architectural or process-design changes require prior discussion.
