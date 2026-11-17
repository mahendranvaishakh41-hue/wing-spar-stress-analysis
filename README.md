# Wing Spar Load and Stress Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mahendranvaishakh41-hue/wing-spar-stress-analysis/blob/main/Wing_Spar_Load_and_Stress_Analysis.ipynb)

A Python tool that estimates the loads on a light aircraft's wing and checks whether the main spar is strong enough at the design load factor (n = 3.8, FAR 23 normal category).

## Method

Schrenk lift distribution → shear force → bending moment → spar root bending stress (σ = My/I) → margins of safety, followed by verification against hand calculations. Built in Python with NumPy and Matplotlib.

## Key results (one wing, n = 3.8)

| Quantity | Result |
|---|---|
| Total lift on one wing | 20,492 N |
| Root shear force | 20,492 N |
| Root bending moment | 45,198 N·m |
| Root bending stress | 240.3 MPa |
| Margin of safety (yield) | 0.44 |
| Margin of safety (ultimate, factor 1.5) | 0.34 |

## Verification

| Check | Python | Hand calculation | Difference |
|---|---|---|---|
| Total lift | 20,492 N | 20,503 N | 0.05% |
| Root bending moment | 45,198 N·m | 45,311 N·m | 0.25% |

## Inputs

| Parameter | Value |
|---|---|
| Aircraft mass | 1,100 kg |
| Wing span / area | 10 m / 16 m² |
| Root / tip chord | 2.0 m / 1.2 m |
| Spar height / flange width | 0.20 m / 0.08 m |
| Flange / web thickness | 12 mm / 4 mm |
| Material | Aluminium 2024-T3 (typical strengths) |

## Assumptions and limitations

Single symmetric pull-up at n = 3.8, with no negative-g or gust cases yet. Lift from Schrenk's approximation. Wing and fuel weight ignored (conservative). The spar carries all the bending. Only root bending stress is checked. Typical, not MMPDS, material strengths. The full list is in the notebook.

## Next steps

Planned additions: flange buckling and web shear checks, negative-g and gust load cases, comparison with XFLR5, and a fatigue life estimate (S-N curve and Miner's rule).

## Why I built this

After my MSc I spent some time away from engineering, and I wanted to get back into it with a project I could build myself. I am interested in aircraft wing structures, especially fatigue and damage tolerance, so I chose a wing spar. I also used this project to relearn Python from the basics. The hardest parts for me were loops and turning the lift into shear force and bending moment step by step. Next I want to add buckling checks and a fatigue life estimate.

## Author

Vaishakh Mahendran, MSc Aerospace Engineering (Teesside University)
