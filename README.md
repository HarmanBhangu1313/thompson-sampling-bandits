# Thompson Sampling for Multi-Armed Bandits

##  Overview
This project implements **Thompson Sampling**, a **Bayesian algorithm** for solving the **multi-armed bandit problem**.  
The objective is to study the **exploration–exploitation tradeoff** using probabilistic posterior sampling rather than heuristic exploration strategies.

The project is implemented on a simulated **ad selection (CTR optimization)** task.

---

##  Key Concepts Covered
- Multi-armed bandit problem
- Exploration vs exploitation
- Bayesian inference
- Posterior sampling
- Bernoulli reward modeling

---

##  Tech Stack
- **Python**
- **NumPy**
- **Matplotlib**

---

##  Project Structure
thompson-sampling-bandits/
|── thompson_sampling.ipynb
├── dataset.csv
|── README.md
|-- requirements.txt

---

##  Algorithm Workflow
1. Initialize Beta priors for each arm
2. Sample a probability from each arm’s posterior
3. Select the arm with the highest sampled value
4. Observe reward (success/failure)
5. Update the posterior distribution
6. Repeat for each timestep

---

##  Algorithm Intuition (Thompson Sampling)
For Bernoulli rewards, each arm’s success probability is modeled using a **Beta distribution**:

P   ~ Beta( ⍺  , β  )
 i           i    i

At each step, a probability is sampled from each posterior, and the arm with the highest sample is selected.

Posterior parameters are updated as:
-  ⍺(i) number of observed successes +1
-  β(i) number of observed failures +1

This probabilistic sampling naturally balances **exploration and exploitation** without explicit tuning parameters.

---

##  Results
- The algorithm converges toward selecting the optimal arm
- Suboptimal arms are explored less frequently over time
- Demonstrates efficient learning compared to random selection

---

##  Notes
- This is a **foundational reinforcement learning project**
- Focus is on algorithmic understanding rather than deep RL
- Rewards are modeled as Bernoulli random variables

---

## Future Improvements
- Compare Thompson Sampling with ε-greedy and UCB
- Plot cumulative regret curves
- Extend to non-stationary bandits
- Explore contextual bandits
