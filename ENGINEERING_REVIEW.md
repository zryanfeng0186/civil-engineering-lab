# Engineering review — lecture-aligned educational version

## Source material used
- `MOMI_2025-2026.pdf`: Mechanics of Materials I, including axial stress/strain, thermal effects, internal loadings, beam shear/moment diagrams, flexural stress, shear stress, torsion, and transformed composite sections.
- `Part 1 - Introduction & Rec Beam by ASD.pdf`: Reinforced Concrete Design for 3rd Stage, ASD method, especially the singly reinforced rectangular-beam assumptions and equations on printed pages 22–28, allowable stresses on page 30, and design/spacing guidance on pages 34–40.

## Checks tied directly to the uploaded lecture
1. **RC ASD worked example (printed pages 26–28):** for `b=300 mm`, `h=500 mm`, `d=420 mm`, `As=1847 mm²`, `f'c=21 MPa`, `fy=414 MPa`, the transformed-section calculations give `Ec=21,538 MPa`, `n=9.286`, neutral-axis ratio `k=0.4031`, `j=0.8656`, and `Mcr≈42.77 kN·m`. At `M=75 kN·m`, calculated `fc≈8.123 MPa` and `fs≈111.69 MPa`, matching the lecture's rounded values `8.12 MPa` and `111.7 MPa`.
2. **Allowable stresses:** the RC analyzer follows the lecture's `fc,allow = 0.45 f'c`, `fs,allow = 140 MPa` when `fy < 400 MPa`, and `fs,allow = 170 MPa` when `fy ≥ 400 MPa`.
3. **Beam diagrams:** the basic four idealized beam cases use standard closed-form shear and moment results and were checked for `L=5 m`, `w=20 kN/m`, or `P=20 kN` as applicable (values below).
4. **T-beam supplementary calculation:** corrected the neutral-axis equation for a neutral axis in the web and corrected the compression-zone second moment of area. The inertia expression was checked against direct integration of the same section. This T-beam module is **not developed in the supplied RC ASD Part 1 file**, so it remains explicitly marked supplementary.
5. **Steel–concrete composite visualization:** fixed an undefined variable in the stress-diagram code. The model states its full-interaction assumption and does not assume composite action when shear connectors are absent.
6. **Design spacing:** added maximum aggregate size to the clear-spacing check because the lecture's page 34 rule includes 25 mm, bar diameter, and maximum aggregate size. The displayed default aggregate size of 20 mm is an illustrative placeholder and must be changed to the class example's value.
7. **Input and wording:** added clearer input checks and separated lecture-aligned ASD work from supplementary strength-design, doubly reinforced, T-beam, shear, and continuous-beam modules that are not established by the supplied RC Part 1 PDF.

## Basic beam benchmark values
For `L = 5 m`, `w = 20 kN/m`, or `P = 20 kN` as appropriate:
- Simply supported, uniform load: `Vmax = 50 kN`, `Mmax = 62.5 kN·m`.
- Simply supported, midspan point load: `Vmax = 10 kN`, `Mmax = 25 kN·m`.
- Cantilever, uniform load: `Vmax = 100 kN`, `Mmax = 250 kN·m`.
- Cantilever, end point load: `Vmax = 20 kN`, `Mmax = 100 kN·m`.

## Remaining limitations
- This was a targeted review, not a complete equation-by-equation audit of every interactive module.
- The supplied RC file is Part 1; it does not establish the later-lecture methods for doubly reinforced beams, T-beams, shear/stirrups, continuous-beam coefficients, or the strength-design illustration. Those cards are marked supplementary and need their corresponding lecture parts to be checked against course-specific methods.
- The app's simplified immediate/long-term deflection, 3D behavior visualization, and material stress–strain curves are teaching illustrations, not validated predictions.
- JavaScript syntax is checked with Node.js. This environment did not complete a full headless browser run, so visual behavior should still be tested locally in a browser after download.
- This is for education only, not construction, permitting, or safety decisions.
