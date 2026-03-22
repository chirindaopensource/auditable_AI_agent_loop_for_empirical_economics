# **`README.md`**

# An Auditable AI Agent Loop for Empirical Economics

<!-- PROJECT SHIELDS -->
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![arXiv](https://img.shields.io/badge/arXiv-2603.17381v2-b31b1b.svg)](https://arxiv.org/abs/2603.17381v2)
[![Journal](https://img.shields.io/badge/Journal-ArXiv%20Preprint-003366)](https://arxiv.org/abs/2603.17381v2)
[![Year](https://img.shields.io/badge/Year-2026-purple)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Discipline](https://img.shields.io/badge/Discipline-Econometrics%20%7C%20Agentic%20AI-00529B)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Data Sources](https://img.shields.io/badge/Data-ECB%20SPF%20%7C%20Eurostat-lightgrey)](https://www.ecb.europa.eu/stats/ecb_surveys/spf/html/index.en.html)
[![Core Method](https://img.shields.io/badge/Method-Evaluator--Locked%20Search-orange)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Analysis](https://img.shields.io/badge/Analysis-peLASSO%20%7C%20Forecast%20Combination-red)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Validation](https://img.shields.io/badge/Validation-Diebold--Mariano%20Test-green)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Robustness](https://img.shields.io/badge/Robustness-Post--Search%20Holdout-yellow)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Type Checking: mypy](https://img.shields.io/badge/type%20checking-mypy-blue)](http://mypy-lang.org/)
[![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=flat&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![SciPy](https://img.shields.io/badge/SciPy-%230C55A5.svg?style=flat&logo=scipy&logoColor=white)](https://scipy.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Anthropic](https://img.shields.io/badge/Anthropic-Claude%20Opus-black)](https://www.anthropic.com/)
[![YAML](https://img.shields.io/badge/YAML-%23CB171E.svg?style=flat&logo=yaml&logoColor=white)](https://yaml.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-%23F37626.svg?style=flat&logo=Jupyter&logoColor=white)](https://jupyter.org/)
[![Open Source](https://img.shields.io/badge/Open%20Source-%E2%9D%A4-brightgreen)](https://github.com/auditable_AI_agent_loop_for_empirical_economics)

**Repository:** `https://github.com/auditable_AI_agent_loop_for_empirical_economics`

**Owner:** 2026 Craig Chirinda (Open Source Projects)

This repository contains an **independent**, professional-grade Python implementation of the research methodology from the 2026 paper entitled **"An Auditable AI Agent Loop for Empirical Economics: A Case Study in Forecast Combination"** by:

*   **Minchul Shin** (Federal Reserve Bank of Philadelphia)

The project provides a complete, end-to-end computational framework for replicating the paper's findings. It delivers a modular, highly optimized pipeline that executes the entire research workflow: from the rigorous ingestion and imputation of macroeconomic survey data to the execution of a cryptographically secure, evaluator-locked AI agent loop, culminating in out-of-sample Diebold-Mariano predictive accuracy testing.

## Table of Contents

- [Introduction](#introduction)
- [Theoretical Background](#theoretical-background)
- [Features](#features)
- [Methodology Implemented](#methodology-implemented)
- [Core Components (Notebook Structure)](#core-components-notebook-structure)
- [Key Callable: `execute_master_pipeline`](#key-callable-execute_master_pipeline)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Input Data Structure](#input-data-structure)
- [Usage](#usage)
- [Output Structure](#output-structure)
- [Project Structure](#project-structure)
- [Customization](#customization)
- [Contributing](#contributing)
- [Recommended Extensions](#recommended-extensions)
- [License](#license)
- [Citation](#citation)
- [Acknowledgments](#acknowledgments)

## Introduction

This project provides a Python implementation of the analytical framework presented in Shin (2026). The core of this repository is the iPython Notebook `auditable_AI_agent_loop_for_empirical_economics_draft.ipynb`, which contains a comprehensive suite of 32+ orchestrated tasks to replicate the paper's findings.

The pipeline addresses the "crisis of transparency" in AI-driven empirical science. While Large Language Models (LLMs) drastically reduce the marginal cost of specification search, they simultaneously explode the "garden of forking paths," masking researcher degrees of freedom. 

The codebase operationalizes the proposed solution:
-   **Formalizes** the research process as a bounded stochastic optimization problem.
-   **Isolates** the LLM agent within a strict Abstract Syntax Tree (AST) execution sandbox, permitting it to edit only a single forecasting script ($\tau$) while the evaluation harness ($S$) remains mathematically immutable.
-   **Coordinates** the autonomous search using a four-file architecture (`program.md`, `train.py`, `prepare.py`, `results.tsv`), enforcing a greedy keep/revert logic via Git version control.
-   **Evaluates** the discovered methodologies (e.g., Partially-Egalitarian LASSO tuning, bias correction) on a strictly air-gapped holdout sample, distinguishing robust structural insights from sample-specific overfitting.

## Theoretical Background

The implemented methods combine techniques from High-Dimensional Econometrics, Agentic AI Engineering, and Secure Systems Architecture.

**1. The Bounded Optimization Problem:**
The theoretical optimum minimizes the scalar score on the search sample $D^S$. The agent loop seeks the realized bounded optimum $\hat{\tau}_K$ within a finite budget of $K$ experiments:
$$ \hat{\tau}_K \in \arg \min_{\tau \in \{\tau_0, \tau_1, \dots, \tau_K\}} S(\tau; D^S) $$

**2. Recursive Rolling-Origin Evaluation:**
To strictly prevent look-ahead bias, the immutable evaluator provides the agent with a sliding window of size $W=20$. At forecast origin $t$, the agent only has access to historical data up to $t-1$:
$$ S(\tau; D^S) = \sqrt{\frac{1}{65}\sum_{t=6}^{70} (y_t - \hat{y}_t)^2} $$

**3. Discovered Econometric Methodologies:**
The pipeline mathematically recreates the specific algorithms discovered by the agent, including Run 2's highly successful bias correction mechanism, which exploits serial correlation in combined forecast errors:
$$ \hat{y}_t = \tilde{y}_t - 0.80 \cdot \hat{e}_n^{LOO,pct} $$

**4. Predictive Accuracy Testing:**
Out-of-sample generalization is evaluated using the Diebold-Mariano test, utilizing a Newey-West HAC variance estimator to account for serial correlation in the loss differential $d_t = e_{SA,t}^2 - e_{method,t}^2$.

Below is a diagram which summarizes the proposed approach:

<div align="center">
  <img src="https://github.com/chirindaopensource/auditable_AI_agent_loop_for_empirical_economics/blob/main/auditable_AI_agent_loop_for_empirical_economics_ipo_main.png" alt="Auditable AI Agent Loop Architecture" width="100%">
</div>

## Features

The provided iPython Notebook (`auditable_AI_agent_loop_for_empirical_economics_draft.ipynb`) implements the full research pipeline, including:

-   **AST-Based Execution Sandboxing:** Untrusted LLM-generated code is compiled and executed within a strictly restricted `globals` dictionary, mathematically guaranteeing the agent cannot access the OS, the filesystem, or the holdout data.
-   **OS-Level Process Group Management:** The evaluator subprocess is bound by a strict 30-minute timeout. Upon exhaustion, the entire process tree is eradicated (via `os.killpg` or `CREATE_NEW_PROCESS_GROUP`), ensuring $O(1)$ resource leakage over hundreds of iterations.
-   **Vectorized Combinatorial Benchmarks:** Exhaustive subset searches (e.g., Best avg flex) are evaluated simultaneously using highly optimized matrix multiplication ($X_{train} M$), bypassing slow Python-level loops.
-   **Configuration-Driven Design:** All study parameters (hyperparameters, temporal bounds, LLM settings) are managed in an external `config.yaml` file.
-   **Cryptographic Archival:** Automatically serializes all artifacts (CSV, JSON, TSV) and generates an immutable `.zip` archive with a master SHA-256 checksum manifest for absolute reproducibility.

## Methodology Implemented

The core analytical steps directly implement the methodology from the paper:

1.  **Data Engineering (Tasks 1-9):** Ingests raw SPF microdata and Eurostat GDP realizations, standardizes temporal indices, performs an audited inner join, imputes missing values (linear interpolation and cross-sectional means), and physically air-gaps the holdout sample.
2.  **Evaluator Construction (Tasks 10-14):** Constructs the 200-point regularization grids, instantiates the look-ahead-free `EvaluatorInfoBuilder`, validates the Simple Average baseline, and establishes the secure editable interface.
3.  **Agentic Orchestration (Tasks 15-19):** Materializes the Markdown instruction contract, initializes the Git audit trail, and manages the autonomous LLM session recovery semantics.
4.  **Benchmark & Method Recreation (Tasks 20-25):** Ports the required R `glmnet` helpers to Python `scikit-learn` (ensuring exact penalty scaling), evaluates the ex-post peLASSO oracles, and mathematically recreates the Run 1, 2, and 3 method families.
5.  **Evaluation & Testing (Tasks 26-29):** Computes in-sample and out-of-sample RMSEs, executes the Diebold-Mariano tests, and performs heuristic NLP analysis on the TSV logs to document methodology drift.
6.  **Robustness & Archival (Tasks 30-32):** Executes the ex-COVID robustness checks, validates the five core scientific conclusions, generates the epistemological fidelity matrix, and freezes the research archive.

## Core Components (Notebook Structure)

The notebook is structured as a logical pipeline with modular orchestrator functions for each of the 32 major tasks. All functions are self-contained, fully documented with strict type hints and comprehensive docstrings, and designed for professional-grade execution.

## Key Callable: `execute_master_pipeline`

The project is designed around a single, top-level user-facing interface function:

-   **`execute_master_pipeline`:** This master orchestrator function runs the entire automated research pipeline from end-to-end. A single call to this function reproduces the entire computational portion of the project, managing data validation, evaluator construction, agentic search (or method recreation), and cryptographic archival.

## Prerequisites

-   Python 3.10+
-   Core dependencies: `pandas`, `numpy`, `scikit-learn`, `scipy`, `pyyaml`.
-   LLM Integration: `anthropic` (requires a valid API key for `discovery` mode).
-   System: `git` must be installed and accessible in the system PATH.

## Installation

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/auditable_AI_agent_loop_for_empirical_economics.git
    cd auditable_AI_agent_loop_for_empirical_economics
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install Python dependencies:**
    ```sh
    pip install pandas numpy scikit-learn scipy pyyaml anthropic
    ```

## Input Data Structure

The pipeline requires two primary data structures, strictly validated at runtime:

1.  **`df_spf_panel_wide` (pd.DataFrame):** A wide panel containing a `date` column (`YYYYQq` format) and 23 forecaster columns (`Float64` nullable type). Missing values are permitted pre-imputation.
2.  **`df_gdp_target_series` (pd.DataFrame):** A time series containing a `date` column and a `real_gdp_growth_yoy` column (`Float64`). Zero missing values are permitted in the target vector.

*Note: The pipeline includes a synthetic data generator for testing purposes if access to the original ECB/Eurostat data is unavailable.*

## Usage

The notebook provides a complete, step-by-step guide. The primary workflow is to execute the final cell, which demonstrates how to load the configuration, generate synthetic data, and use the top-level orchestrator in `holdout_evaluation` mode (bypassing the expensive LLM API calls while rigorously testing the deterministic kernel):

```python
import os
import yaml
import pandas as pd
import numpy as np

# 1. Load the master configuration from the YAML file.
# (Assumes config.yaml is in the working directory)
with open("config.yaml", "r", encoding="utf-8") as f:
    study_config = yaml.safe_load(f)

# 2. Load raw datasets (Example using synthetic generator provided in the notebook)
# In production, load from CSV: pd.read_csv("data/spf_raw.csv")
df_spf_panel_wide, df_gdp_target_series = generate_synthetic_econometric_data()

# 3. Execute the entire replication study.
master_results = execute_master_pipeline(
    df_spf_panel_wide=df_spf_panel_wide,
    df_gdp_target_series=df_gdp_target_series,
    study_configuration=study_config,
    mode="holdout_evaluation",
    output_directory="./reproducibility_archive",
    data_provenance="synthetic_demonstration",
    declared_panel_scope="full_panel"
)

# 4. Access results
if master_results.get("master_status") == "SUCCESS":
    report_30 = master_results["task_30_report"]
    
    print("\n[*] Out-of-Sample Results: Holdout Sample (2017Q1-2025Q4)")
    print(report_30.holdout_rmse_table[["method_name", "holdout_rmse", "holdout_relative_rmse"]].head().to_string(index=False))
    
    print("\n[*] Diebold-Mariano Predictive Accuracy Summary")
    print(report_30.dm_summary_table[["method_name", "holdout_rmse_formatted"]].head().to_string(index=False))
    
    report_32 = master_results["task_32_report"]
    print(f"\n[*] Archive frozen at: {report_32.archive_path}")
```

## Output Structure

The pipeline returns a master dictionary containing:
-   **`task_30_report`**: The core pipeline artifacts, including the cleansed data, imputation audits, benchmark registries, and the comprehensive in-sample and out-of-sample RMSE evaluation tables.
-   **`task_31_report`**: The robustness analysis artifacts, including the ex-COVID validation records and the ordinal ranking preservation memo.
-   **`task_32_report`**: The final capstone artifacts, including the empirical verification of the 5 scientific conclusions, the epistemological fidelity classification matrix, and the absolute path to the cryptographic `.zip` archive.

## Project Structure

```
auditable_AI_agent_loop_for_empirical_economics/
│
├── auditable_AI_agent_loop_for_empirical_economics_draft.ipynb   # Main implementation notebook
├── config.yaml                                                   # Master configuration file
├── requirements.txt                                              # Python package dependencies
│
├── LICENSE                                                       # MIT Project License File
└── README.md                                                     # This file
```

## Customization

The pipeline is highly customizable via the `config.yaml` file. Users can modify study parameters such as:
-   **Agent Constraints:** Adjust the search budget ($K$), the timeout limit, or the allowed Python packages in the sandbox.
-   **Econometrics:** Alter the rolling window size ($W$), the resolution of the $\lambda$ grid, or the specific quarters excluded during robustness checks.
-   **LLM Settings:** Switch the coding assistant model (e.g., from Claude Opus to GPT-4) or adjust the temperature and top-p parameters.

## Contributing

Contributions are welcome. Please fork the repository, create a feature branch, and submit a pull request with a clear description of your changes. Adherence to PEP 8, strict type hinting, and the 1:1 inline comment-to-code-line ratio is required.

## Recommended Extensions

Future extensions could include:
-   **Alternative Search Strategies:** Replacing the greedy local search with evolutionary population-based search (e.g., AlphaEvolve) or Monte Carlo Tree Search (MCTS).
-   **Expanded Econometric Domains:** Adapting the immutable evaluator to score Structural VAR identification schemes or real-time Phillips curve specifications, as outlined in the paper's schematic extensions.
-   **Formal Post-Selection Inference:** Integrating rigorous statistical frameworks to correct for the p-hacking inherent in the agent's high-speed specification search.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Citation

If you use this code or the methodology in your research, please cite the original paper:

```bibtex
@article{shin2026auditable,
  title={An Auditable AI Agent Loop for Empirical Economics: A Case Study in Forecast Combination},
  author={Shin, Minchul},
  journal={arXiv preprint arXiv:2603.17381v2},
  year={2026}
}
```

For the implementation itself, you may cite this repository:
```
Chirinda, C. (2026). An Auditable AI Agent Loop for Empirical Economics: An Open Source Implementation.
GitHub repository: https://github.com/auditable_AI_agent_loop_for_empirical_economics
```

## Acknowledgments

-   Credit to **Minchul Shin** for the foundational research that forms the entire basis for this computational replication.
-   Credit to **Andrej Karpathy** for the original `autoresearch` open-source agent-loop architecture upon which this econometric adaptation is built.
-   This project is built upon the exceptional tools provided by the open-source community. Sincere thanks to the developers of the scientific Python ecosystem, particularly the **scikit-learn** and **pandas** contributors.

--

*This README was generated based on the structure and content of the `auditable_AI_agent_loop_for_empirical_economics_draft.ipynb` notebook and follows best practices for research software documentation.*
