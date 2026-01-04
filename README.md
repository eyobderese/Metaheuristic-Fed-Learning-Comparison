# README: Federated Learning Metaheuristic Comparison

## 1. Project Objective

This project benchmarks three nature-inspired algorithms (NIAs) against the state-of-the-art **FedProx** baseline. The goal is to optimize **Client Selection** in a heterogeneous Federated Learning environment.

## 2. Experimental Environment

- **Platform:** Kaggle (Notebook)
- **Dataset:** **MNIST** (Handwritten Digits)

- **Partitioning:** 100 Clients.

- **Data Distribution:** Non-IID (Each client receives only 2 classes of digits).

- **Model Architecture:** Multi-Layer Perceptron (MLP)
- Input: 784 nodes.

- Hidden: 2 layers (200, 100 nodes) with ReLU.
- Output: 10 nodes (Softmax).

---

## 3. Implementation Requirements

Each algorithm will attempt to select the **optimal subset of 10 clients** per communication round.

| Category               | Algorithm to Implement           | Source Requirement |
| ---------------------- | -------------------------------- | ------------------ |
| **SOTA Baseline**      | <br>**FedProx**                  |                    |
| **Evolutionary**       | <br>**Genetic Algorithm (GA)**   |                    |
| **Swarm Intelligence** | <br>**Particle Swarm (PSO)**     |                    |
| **Physics-based**      | <br>**Simulated Annealing (SA)** |                    |

---

## 4. One-Week Execution Timeline

### Day 1-2: Data & Baseline (SOTA)

- **Task 1:** Pre-process MNIST into 100 Non-IID shards.

- **Task 2:** Implement the **FedProx** loss function:

where .

- **Task 3:** Run 50–100 rounds of FedProx with random client selection to establish the baseline.

### Day 3-5: Metaheuristic Implementation

- **Task 4:** Define the **Fitness Function**: The global model accuracy on a small validation set after one training round with the selected clients.

- **Task 5 (GA):** Use binary encoding (100-bit string) to represent client selection.

- **Task 6 (PSO):** Optimize a 100-dimension vector representing the probability of selection.

- **Task 7 (SA):** Implement a temperature-based acceptance for swapping clients in the active set.

### Day 6-7: Evaluation & Comparison

- **Task 8:** Generate **Convergence Curves** (Fitness/Accuracy vs. Rounds) for all four methods.

- **Task 9:** Perform the **Wilcoxon rank-sum test** to check for statistical significance.

- **Task 10:** Draft the **Findings** section for the LNCS paper.

---

## 5. Expected Deliverables (for Paper)

1.  **Mathematical definition** of the fitness function used for NIAs.

2.  **Hardware & Dataset specs** (Kaggle P100/T4, MNIST).

3.  **Comparative plots** showing if any NIA beat FedProx.
