# Targeted calculation checks

These are narrow regression checks for the educational model, not a full validation of every module.

## RC ASD example from the uploaded lecture
Inputs: b = 300 mm, h = 500 mm, d = 420 mm, As = 1847 mm², f'c = 21 MPa, fy = 414 MPa, M = 75 kN·m.

| Quantity | App calculation | Lecture value |
|---|---:|---:|
| Ec | 21,538 MPa | 21,538 MPa (rounded) |
| Modular ratio n | 9.29 | 9.3 (rounded) |
| Neutral-axis ratio k | 0.403 | 0.403 (rounded) |
| Concrete compression stress | 8.12 MPa | 8.12 MPa |
| Steel tension stress | 111.7 MPa | 111.7 MPa |
| Cracking moment Mcr | 42.8 kN·m | 42.8 kN·m (calculated in the lecture) |

## Elementary beam cases
Using L = 5 m and w = 20 kN/m or P = 20 kN as appropriate:

| Case | Expected Vmax | Expected Mmax | Result |
|---|---:|---:|---|
| Simply supported, uniform load | 50 kN | 62.5 kN·m | Pass |
| Simply supported, midspan point load | 10 kN | 25 kN·m | Pass |
| Cantilever, uniform load | 100 kN | 250 kN·m | Pass |
| Cantilever, end point load | 20 kN | 100 kN·m | Pass |

## Additional regression checks
- JavaScript syntax check passes (`node --check`).
- Startup execution was exercised with a minimal DOM harness; the previously undefined composite stress variable no longer throws.
- The T-beam neutral-axis solution and transformed cracked-section inertia agree with direct integration for the tested default section. This module remains supplementary because the supplied RC ASD Part 1 lecture does not cover it.

The application still needs a real-browser visual pass on desktop/mobile and course-specific review of the supplementary modules.
