# Contributing Guidelines (`CONTRIBUTING.md`)

Thank you for your interest in the **SolarDes Test Stand — SCADA Training Simulator**!

## What We Welcome
- **Bug Reports:** Fixes for JavaScript errors, browser compatibility issues, UI layout glitches on mobile/tablet screens, or typos in documentation.
- **Thermodynamic & Unit Verification:** Reports of any unit mismatches or numerical edge cases in the open thermodynamic formulas (`PhysicsEngine`).
- **Accessibility & Localization:** Improvements to keyboard navigation, screen-reader labels, or translations.

## What Requires Prior Discussion
- **Do Not Alter Process Architecture Without Discussion:** This simulator follows a specific 5-stage laboratory SOP training curriculum. Please do not submit pull requests that remove SOP gates, alter the 16-channel sensor matrix layout, or replace the single-file zero-dependency HTML architecture without opening an Issue first.
- **Keep Parameters Illustrative:** Do not hardcode proprietary plant data into pull requests. All process constants must remain inside the top-level `CONFIG` object with clear `illustrative` comments.

## License of Contributions
By submitting a contribution to this repository, you agree that your contribution will be licensed under the **Apache License, Version 2.0** (see `LICENSE`).
