# 🌋 Self-Organised Criticality in Heat Exchangers

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Status](https://img.shields.io/badge/Status-Research_Project-green)
![Model](https://img.shields.io/badge/Model-BTW_Sandpile-orange)
![Field](https://img.shields.io/badge/Field-Complexity_Science-red)

> Simulation of fouling dynamics in shell-and-tube heat exchangers using
> **Self-Organised Criticality (SOC)** and avalanche modelling.

------------------------------------------------------------------------

## 🚀 Why this project?

Industrial heat exchangers degrade slowly and then suddenly lose
performance.\
This project shows fouling behaves like a **complex system at
criticality**:

-   Small events occur frequently\
-   Large failures are rare but inevitable\
-   Gaussian models underestimate risk

We model this using the **Bak--Tang--Wiesenfeld (BTW) sandpile model**.

------------------------------------------------------------------------

## 🧠 Concept

  Heat Exchanger Physics        SOC Analogy
  ----------------------------- -----------------------
  Random fouling deposition     Slow external driving
  Critical fouling resistance   Toppling threshold
  Deposit detachment            Avalanche
  Tube interactions             Network connectivity
  Cleaning/loss at edges        Boundary dissipation

------------------------------------------------------------------------

## 🎯 Objectives

-   Apply complexity science to heat exchanger fouling\
-   Simulate avalanche dynamics using a lattice model\
-   Analyse avalanche size distributions\
-   Study tube connectivity effects\
-   Extract engineering insights

------------------------------------------------------------------------

## ⚙️ Simulation Overview

  Parameter      Value
  -------------- -----------------
  Grid size      15 × 15
  Threshold      zc = 4
  Drive steps    5000
  Connectivity   k = 4 and k = 8
  Boundary       Open

------------------------------------------------------------------------

## 📊 Key Results

-   System evolves to a **Self‑Organised Critical state**
-   Avalanche sizes follow **power‑law distribution**
-   Higher connectivity → larger cascades
-   Large fouling events are **rare but unavoidable**

------------------------------------------------------------------------

## 🛠 Tech Stack

-   Python\
-   NumPy\
-   Matplotlib

------------------------------------------------------------------------

## 📂 Project Structure

soc-heat-exchanger │ ├── simulation.py ├──
Individual_Project_Enhanced.pdf ├── figures/ └── README.md

------------------------------------------------------------------------

## ▶️ How to Run

Clone repo: git clone
https://github.com/YOUR_USERNAME/soc-heat-exchanger.git

Install dependencies: pip install numpy matplotlib

Run simulation: python simulation.py

------------------------------------------------------------------------

## 💡 Engineering Insights

-   Heat exchangers operate near a critical state\
-   Preventive cleaning beats reactive maintenance\
-   Tube connectivity is a design risk parameter

------------------------------------------------------------------------

## 👨‍💻 Author

**Deependra Singh**

⭐ If you like this project, give it a star!
