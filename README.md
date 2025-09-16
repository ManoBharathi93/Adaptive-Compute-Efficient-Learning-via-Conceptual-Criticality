# Adaptive-Compute-Efficient-Learning-via-Conceptual-Criticality
This repository contains the official implementation of our experiments on Criticality Estimation and Early Exit Transformers, developed as part of our research on adaptive, compute-efficient inference for LLMs.

### Notebooks

We provide clean, runnable notebooks so reviewers and researchers can directly explore and reproduce our results:

1. CriticalityModule.ipynb

Implements our pre-compute criticality module.

Uses an entropy-based method to assign a continuous difficulty score (0.0–1.0) for each input.

Inputs with low entropy (high confidence) are marked as “easy,” while high-entropy inputs are marked as “hard.”

Demonstrates how criticality can guide adaptive compute allocation before inference.

2. EarlyExit.ipynb

Implements a Transformer with early exit heads.

During inference, the model sequentially evaluates exit heads and stops computation once confidence ≥ τ (threshold).

Shows clear trade-offs between accuracy, average layers used, and latency per sample.

Includes baseline vs. early-exit comparison plots (Accuracy vs. Layers, Accuracy vs. Latency).

### How to Run

1. Clone the repository:

   
``
git clone https://github.com/ManoBharathi93/Adaptive-Compute-Efficient-Learning-via-Conceptual-Criticality
``


``
cd Adaptive-Compute-Efficient-Learning-via-Conceptual-Criticality
``


``
pip install -r requirements.txt
``

2. Open the notebooks in Jupyter or Colab and run step by step:

   2.1. Start with CriticalityModule.ipynb (to see how criticality is estimated).



   2.2. Then run EarlyExit.ipynb (to see compute savings in action).


## Tentative Repository Organization
```
Adaptive-Compute-Efficient-Learning-via-Conceptual-Criticality
├─ CITATION.cff
├─ README.md
├─ SECURITY.md
├─ CODEOWNERS
├─ LICENSE
├─ environment.yml
├─ project.toml
├─ requirements.txt
├─ benchmarks
│  ├─ leaderboard.md
│  ├─ results
│  └─ tasks
├─ configs
│  ├─ defaults.yaml
│  ├─ inference.yaml
│  │  ├─ early_exit.yaml
│  │  ├─ quant_aware.yaml
│  │  ├─ token_pruning.yaml
│  │  └─ tosa.yaml
│  ├─ model
│  │  ├─ llama8b.yaml
│  │  └─ pythia1b.yaml
│  └─ task
│     ├─ arc.yaml
│     ├─ gsm8k.yaml
│     └─ qa.yaml
├─ data
│  └─ README.md
├─ docs
│  ├─ notes
│  ├─ overleaf_link.md
│  └─ references.bib
├─ notebooks
│  └─ demo.ipynb
├─ scripts
│  ├─ download_gsm8k.sh
│  ├─ setup_env.sh
│  └─ train.sh
├─ src
│  └─ criticality
│     ├─ baselines
│     │  ├─ fixed_early_exit.py
│     │  ├─ random_routing.py
│     │  └─ static_full_compute.py
│     ├─ datasets
│     │  ├─ gsm8k.py
│     │  ├─ mnist_entropy_demo.py
│     │  └─ __init__.py
│     ├─ inference
│     │  ├─ instrumentation.py
│     │  ├─ run_adaptive.py
│     │  └─ run_baseline.py
│     ├─ metrics
│     │  ├─ adaptive_behavior.py
│     │  ├─ cost
│     │  │  ├─ energy.py
│     │  │  ├─ flops.py
│     │  │  ├─ latency.py
│     │  │  └─ macs.py
│     │  └─ task_metrics.py
│     ├─ models
│     │  ├─ adapters
│     │  │  ├─ early_exit.py
│     │  │  ├─ quant_aware.py
│     │  │  ├─ token_pruning.py
│     │  │  └─ tosa_selector.py
│     │  ├─ backbones
│     │  │  ├─ llama.py
│     │  │  └─ pythia.py
│     │  ├─ classifiers
│     │  │  └─ lstm.py
│     │  ├─ policies
│     │  │  ├─ routing_policy.py
│     │  │  └─ thresholds.py
│     │  └─ __init__.py
│     ├─ training
│     │  ├─ losses.py
│     │  ├─ train_baseline.py
│     │  └─ train_classifier.py
│     ├─ utils
│     │  └─ logging.py
│     └─ __init__.py
└─ tests
   ├─ integration
   │  └─ end2end.py
   └─ unit
      ├─ test_entropy.py
      ├─ test_flops.py
      ├─ test_router_head.py
      └─ test_routing_policy.py

```
