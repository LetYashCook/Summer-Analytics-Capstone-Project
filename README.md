# 🚗 Dynamic Pricing for Urban Parking Lots

Capstone Project for **Summer Analytics 2025**  
Organized by: Consulting & Analytics Club × Pathway

## 📌 Project Overview
Urban parking spaces are often underpriced or overpriced due to static pricing. This leads to either overcrowding or underutilization. This project simulates a **real-time dynamic pricing system** for 14 urban parking lots using economic principles and data-driven modeling.

We implement **three progressively intelligent pricing models** using Python, Pandas, NumPy, and Pathway — and visualize them in real time using Bokeh.

## 🧠 Project Objectives
- Design a dynamic pricing engine that:
  - Adapts in real time
  - Responds to demand, congestion, queue length, and nearby competitor prices
  - Suggests intelligent pricing while avoiding erratic fluctuations
- Build 3 models:
  - Baseline (linear)
  - Demand-based (multi-feature)
  - Competitive (geospatial + pricing awareness)
- Simulate real-time pipeline using Pathway
- Visualize prices using interactive Bokeh plots

## 🧰 Tech Stack

| Tool      | Purpose                         |
|-----------|---------------------------------|
| Python    | Main programming language       |
| Pandas    | Data manipulation               |
| NumPy     | Numerical computations          |
| Pathway   | Real-time data stream simulation|
| Bokeh     | Real-time visualization         |
| Google Colab | Notebook environment         |
| GitHub    | Code repository and documentation|

## 🧱 Architecture Diagram

graph TD
    A[Parking Dataset (CSV)] --> B[Preprocessing]
    B --> C1[Model 1: Linear Pricing]
    B --> C2[Model 2: Demand-Based Pricing]
    B --> C3[Model 3: Competitive Pricing]
    C1 --> D[Real-Time Price Stream]
    C2 --> D
    C3 --> D
    D --> E[Bokeh Visualization]
    
 Model 1: Baseline Linear Pricing
A simple model where price increases with occupancy.
Formula:
Price = BasePrice + α × (Occupancy / Capacity)
Base Price = $10
α = Scaling factor (e.g., 5.0)

Model 2: Demand-Based Pricing
Uses a weighted demand function based on:
-Occupancy ratio
-Queue length
-Traffic condition
-Special day flag
-Vehicle type (car/bike/truck)

Formula:
Price = BasePrice × (1 + λ × NormalizedDemand)
Where NormalizedDemand is scaled between 0 and 1

Capped to:
Minimum = 0.5 × base
Maximum = 2 × base

Model 3: Competitive Pricing (Optional + Rewarded)
Adds intelligence by comparing each lot to nearby lots within 1 km.
Logic:

If nearby lots are cheaper → reduce price slightly
If nearby lots are expensive/full → increase price
Distance calculated using: Haversine formula

📈 Visualizations
All models include Bokeh plots showing real-time pricing trends per lot.
Interactive charts allow users to hover and compare across timestamps.
