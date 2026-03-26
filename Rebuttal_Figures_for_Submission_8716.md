# Figure R1: Vector Field and Jacobian Norm Comparison (2D Toy with Q-Guidance)

![Figure R1](fig_R1_heatmaps.png)

# Figure R2: Jacobian Norm Across Trajectory and Training Loss Components

![Figure R2](fig_R2_stats.png)

# Figure R3: ODE Trajectories with Q-Guidance

![Figure R3](fig_R3_trajectories.png)

# Figure R4: PQL Training Loss Decomposition (pen-human-v1, 500K steps)

![Figure R4](fig_R4_loss_decomposition.png)

# Figure R5: Gradient Cosine Similarity Between $\nabla L_{FM}$ and $\nabla L_{PDE}$

![Figure R5](fig_grad_cosine_R5.png)

# Figure R6: Training Curves with Ablations (mean ± std, 8 seeds) on Pen-Human, Antmaze-Large, and Antsoccer-Arena.

![Figure R6](fig_R6_training_curves.png)

---

## Table R1: Aggregated Performance (Macro-Average per Suite)

| Algorithm | D4RL Gym-MuJoCo | Adroit | OGBench |
|---|:-:|:-:|:-:|
| BC | 51.9 | 36.8 | 0.6 |
| IQL | 77.1 | 53.6 | 18.3 |
| CQL | 64.0 | 40.3 | 14.1 |
| IDQL | 78.2 | 52.2 | 17.7 |
| SRPO | **86.8** | 50.7 | 12.5 |
| CAC | 81.9 | 42.9 | 20.5 |
| FQL | 33.6 | 51.6 | 38.6 |
| FAWAC | — | 48.2 | 12.1 |
| FBRAC | — | 50.0 | 27.7 |
| IFQL | — | 52.4 | 22.5 |
| Flow | 79.4 | — | — |
| CNF | 82.0 | — | — |
| **PQL (Ours)** | 85.2 | **57.9** | **42.7** |

---

## Table R2: Stability Comparison — Standard Deviation over 8 Seeds (PQL vs PQL w/o PDE Regularizer)

| Environment | PQL Mean | PQL Std | PQL-PDE Mean | PQL-PDE Std | Std Reduction |
|---|---|---|---|---|---|
| **D4RL Gym-MuJoCo** | | | | | |
| HalfCheetah-ME | 90.2 | 1.4 | 84.3 | 4.9 | 71% |
| HalfCheetah-M | 54.1 | 2.2 | 45.1 | 3.5 | 37% |
| HalfCheetah-MR | 51.3 | 0.3 | 45.2 | 2.4 | 88% |
| Hopper-ME | 111.8 | 2.9 | 102.4 | 3.8 | 24% |
| Hopper-M | 84.2 | 1.1 | 79.5 | 1.9 | 42% |
| Hopper-MR | 92.1 | 3.4 | 88.6 | 3.9 | 13% |
| Walker2d-ME | 114.4 | 0.8 | 109.8 | 1.9 | 58% |
| Walker2d-M | 86.2 | 3.1 | 82.0 | 3.5 | 11% |
| Walker2d-MR | 84.4 | 1.2 | 80.1 | 2.1 | 43% |
| **Adroit** | | | | | |
| Pen-Human | 82.0 | 3.0 | 53.0 | 12.0 | 75% |
| Pen-Cloned | 87.0 | 6.0 | 72.0 | 11.0 | 45% |
| Pen-Expert | 148.0 | 7.0 | 143.0 | 4.0 | −75% |
| Hammer-Cloned | 14.0 | 6.0 | 11.0 | 9.0 | 33% |
| Hammer-Expert | 134.0 | 1.0 | 123.0 | 3.0 | 67% |
| **OGBench** | | | | | |
| Antmaze-Large | 84.0 | 7.0 | 77.0 | 28.0 | 75% |
| Antmaze-Giant | 7.0 | 1.0 | 5.0 | 3.0 | 67% |
| Humanoid-Medium | 30.0 | 10.0 | 20.0 | 11.0 | 9% |
| Antsoccer-Arena | 41.0 | 15.0 | 40.0 | 31.0 | 52% |
| Cube-Double | 41.0 | 4.0 | 35.0 | 7.0 | 43% |
| Scene-Play | 80.0 | 3.0 | 77.0 | 8.0 | 63% |

---

## Table R3: Cross-Method Generalization — FBRAC ($\lambda=0.015$)

| Config | Pen-Human | Antmaze-Large |
|---|---|---|
| FBRAC (original) | $77\pm7$ | $70\pm20$ |
| FBRAC + PDE only | $74\pm5$ | $66\pm13$ |
| FBRAC + PDE + Beta | **$82\pm4$** | **$75\pm10$** |

---

## Table R4: Alternative Timestep Distributions (pen-human-v1, $\lambda=0.015$)

| Distribution + PDE | Pen-Human |
|---|---|
| Uniform | $75\pm8$ |
| Truncated normal | $74.3\pm5$ |
| Logit-normal | $71.2\pm4$ |
| **Beta(3,3)** | **$82\pm3$** |
