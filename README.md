# 🧬 Agent-Based Simulation of Disease Spread in a Spatial Population

This repository implements an **agent-based model (ABM)** for simulating the spread of infectious diseases in a spatially distributed population using the **SEIRS** and **SEIRD** epidemiological frameworks. The simulation considers spatial proximity, stochastic transitions, and varying epidemiological parameters to mimic realistic disease dynamics.

---

## 📌 Project Objective

To develop and simulate the spread of a contagious disease using an **agent-based model** on a synthetic population of 7,500 agents with spatial and network interactions, capturing the effects of:

- Incubation period
- Infectious period
- Temporary immunity (SEIRS)
- Death (SEIRD)
- Local contacts and small-world connectivity
- Policy interventions (lockdown, distancing)

---

## 🔬 Epidemiological Models

### ✅ SEIRS Model


- Includes **waning immunity**, enabling repeated infection cycles.
- Captures resurgence patterns due to loss of immunity over time.

### ✅ SEIRD Model


- Incorporates **mortality**, allowing permanent removal of agents.
- Severe outbreaks can collapse if many susceptible individuals die.

---

## 🧮 Input Data & Parameters

| Parameter                  | Value/Distribution               | Source                        |
|---------------------------|----------------------------------|-------------------------------|
| Population size           | 7,500 agents                     | Synthetic                     |
| Initial infected          | 10 (random assignment)           | -                             |
| Spatial model             | Uniform distribution             | Synthetic                     |
| Network model             | Small-world                      | Modeled for realism           |
| Latent period (E)         | 3–6 days (uniform)               | CDC COVID-19                  |
| Infectious period (I)     | 5–10 days (uniform)              | CDC Influenza                 |
| Immunity duration (R→S)   | 2–3 months (uniform)             | Healthline                    |
| Transmission probability  | 0.1 per contact                  | PMC Studies                   |

---

## 🔁 Simulation Workflow

1. **Initialization**  
   - Uniformly place agents in space  
   - Randomly infect a subset of agents  
   - Build spatial contact graph (1 km radius)

2. **Daily Simulation Loop**  
   - Agents contact nearby neighbors  
   - SEIRS/SEIRD transitions occur per epidemiological rules  
   - Record all state transitions (S, E, I, R, D)

3. **Output & Visualization**  
   - Time series: infected, recovered, deceased  
   - Animated visualizations of disease spread  
   - Epidemic curves & scenario comparisons  

---

## 📊 Scenario Analysis

### 🔍 What-if Experiments

- **Varying Contact Rates**:  
  - More contacts → faster outbreaks  
  - Less contacts → flattened curve  

- **Lockdown Simulation**:  
  - Reduce spatial radius or network degree  
  - Evaluate intervention timing  

- **Variable Immunity (SEIRS)**:  
  - Shorter immunity → multiple waves  

---

## 💡 Key Findings

| Model | Insights |
|-------|---------|
| **SEIRS** | Recurrent outbreaks possible; immunity duration is critical |
| **SEIRD** | High mortality can stop transmission but at great societal cost |

> **Policy Takeaway:**  
> Early interventions and immunity boosting (e.g., via vaccination) are crucial to reduce peak loads and long-term epidemic burden.

---

## 🛠 Technologies Used

- Python (NumPy, NetworkX, Matplotlib)
- AnyLogic (for animation, optional)
- Synthetic spatial and graph data

---

## 📚 References

1. Roy et al., "Predict COVID-19 Death Rate in Bangladesh," RAAICON, 2021  
2. Wen et al., "Cascade SEIRD Model," BIBM, 2020  
3. Jiang et al., "COVID-19 Outbreak in Beijing via SEIR," CAC, 2020  

---

## 🙏 Acknowledgements

Special thanks to health data sources (CDC, Healthline, PMC) and the original research community for epidemiological parameter estimation.

---

