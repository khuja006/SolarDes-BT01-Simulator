# 5-Stage SOP & 7-Gate Training Structure (`docs/sop-structure.md`)

> **Disclaimer:** All threshold numbers in this document are **illustrative industry training values**.

## 1. Stage-by-Stage Mandatory PASS Gates

| Stage | Name | Gate Condition (Illustrative) | Consequence of Gate Failure |
| :--- | :--- | :--- | :--- |
| **Stage 1** | Mechanical Assembly & Optics | 9-point surface $\Delta T \le 8.0\%$ | Blocks Stage 4 & Stage 5; marks Criterion #1 `FAIL` |
| **Stage 2** | 16-Channel Sensor Calibration | 2-point verification ($0/100^\circ\text{C}$, Tare, $100/500\text{ g}$) | Logged in operator journal |
| **Stage 3** | 24-Hour Vacuum Leak-Test | $\Delta P / \Delta t < 0.20\text{ kPa/h}$ from $25.0\text{ kPa}$ | Blocks Stage 4 & Stage 5 with red lockout banner |
| **Stage 4** | Clean Water Baseline ($h_0$) | Distilled water 6h test ($h_0 = 0.061\text{ kW/(m}^2\cdot\text{K)}$) | Unlocks 30-day seawater trial |
| **Stage 5** | 30-Day Seawater Trial (Phases A–D) | Maintain $h_{\text{eff}} \ge 0.80 \cdot h_0$ ($0.0488\text{ kW/(m}^2\cdot\text{K)}$) | If Phase A scaling drops $>20\%$, Phase B is locked until manual inspection/cleaning |

## 2. The 7 Educational "Construction Go" Criteria

In the simulator, the final scorecard evaluates 7 operational readiness indicators dynamically:

1. **Optical Uniformity:** $\Delta T \le 8.0\%$ across the absorber surface.
2. **Vacuum Integrity:** Leak rate $< 0.20\text{ kPa/h}$ over 24 hours.
3. **Thermal Performance Retention:** $h_{\text{eff}} \ge 80\%$ of clean baseline $h_0$.
4. **Parasitic Flush Water Ratio:** Back-flush water consumption $\le 5\%$ of total feed.
5. **Absorber Material Stability:** Weekly carbon coupon ($M_2$) mass loss $\le 5\%$.
6. **Distillate Water Quality:** $\text{TDS} < 50\text{ mg/L}$ and $\text{NH}_3 < 1.5\text{ mg/L}$ (salicylate method).
7. **Data & Telemetry Integrity:** Zero unresolved sensor disconnects (`-999` error codes).
