# Adaptive-Compute-Efficient-Learning-via-Conceptual-Criticality

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