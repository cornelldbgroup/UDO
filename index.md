# UDO: The Universal Database Optimizer

UDO is the Swiss Army knife of database optimizer tools: it optimizes index selections, tunes system parameters, and picks between semantically equivalent stored procedures. The input is a workload to optimize, together with a performance metric. The output is a configuration (indexes, parameters, ...) that optimizes this metric.

UDO iteratively tries out database configurations and measures performance. It uses reinforcement learning to select the configuration to try next, guided by performance results of prior configurations. The only problem: switching from one configuration to another one (e.g., by creating and dropping indexes) can be expensive! 

To reduce re-configuration overheads, UDO deliberately delays the evaluation of configurations. It waits until enough similar configurations are selected. Then, it uses cost-based optimization to pick an evaluation order that minimizes re-configuration overheads. This process is enabled by a reinforcement learning algorithm that can handle delays between actions and rewards. 

We presented a reinforcement learning algorithm that handles delays (among other challenges) at AAAI 2022. UDO was demoed at VLDB 2021, the full paper will be presented at VLDB 2022.

# Publications

**VLDB 2022** UDO: universal database optimization using reinforcement learning. _J. Wang, I. Trummer, D. Basu_.

**AAAI 2022** Procrastinated tree search: black-box optimization with delayed, noisy, and multi-fidelity feedback. _J. Wang, D. Basu, I. Trummer_.

**VLDB 2021** Demonstrating UDO: a unified approach for optimizing transaction code, physical design, and system parameters via reinforcement learning. _J. Wang, I. Trummer, D. Basu_.

# Team

- Junxiong Wang (Cornell University)
- Immanuel Trummer (Cornell University)
- Debabrota Basu (INRIA)

# Funding

This project is funded by NSF 1910830 (PI: Immanuel Trummer).
