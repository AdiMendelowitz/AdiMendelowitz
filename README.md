# Adi Mendelowitz

[![Website](https://img.shields.io/badge/website-adimendelowitz.dev-2b6cb0)](https://adimendelowitz.dev)
[![Blog](https://img.shields.io/badge/blog-blog.adimendelowitz.dev-2b6cb0)](https://blog.adimendelowitz.dev)
[![TMLR 2026 paper](https://img.shields.io/badge/paper-TMLR%202026-b31b1b)](https://openreview.net/forum?id=aiUZ2y8UNl)

I'm a senior data scientist working on forecasting, anomaly detection and experiment design for operational data, and each project below links to its code, tests and results.

## Selected work

### [cd-ci-patchtst](https://github.com/AdiMendelowitz/cd-ci-patchtst): channel dependence in PatchTST

My paper in TMLR (2026) asks whether letting a forecasting model look at every channel at once is worth what it costs to train. On controlled synthetic data, accuracy stayed inside a 1% band fixed in advance, while a channel-dependent epoch on the ECL dataset took 6.7 times as long. The cheaper per-channel model was the better choice in every setting I tested, and the repository rebuilds every number in the paper in under a minute on a CPU.

<p align="center">
  <img src="https://raw.githubusercontent.com/AdiMendelowitz/cd-ci-patchtst/main/paper/figures/heatmap.png" width="360" alt="Ratio of channel-dependent to channel-independent test error across nine synthetic settings, three channel counts by three correlation strengths. Every cell lies between 0.998 and 1.006, so neither mode is meaningfully more accurate.">
</p>

### [ab-test-forensics](https://github.com/AdiMendelowitz/ab-test-forensics): how A/B tests reach the wrong decision

Case studies of experiments that went wrong, each built on data with a known ground truth so the damage can be measured. In the first case, lost scan logs make the dashboard's reading look like a win, while the analysis of every routed product stays inside the noise. There is a [blog post](https://blog.adimendelowitz.dev/ab-test-forensics/lost-logs-found-lift-part-1.html) that walks through it.

<p align="center">
  <img src="https://raw.githubusercontent.com/AdiMendelowitz/ab-test-forensics/main/case_studies/01_lost_logs_found_lift/figures/fig3_naive_vs_itt.png" width="520" alt="The same experiment read on two populations: the analysis of all routed products gives a lift of +1.9% with an interval crossing zero, while the dashboard's population of products with a logged scan gives +5.5%, clearing the +1% ship threshold.">
</p>

### [applied-ml](https://github.com/AdiMendelowitz/applied-ml): implementations from scratch

PyTorch and NumPy code I wrote across computer vision, adversarial attacks and forecasting, with 225 tests. One result I like: static INT8 quantisation made a ResNet-18 3.95 times smaller and 1.52 times faster at the same accuracy.

<p align="center">
  <img src="https://raw.githubusercontent.com/AdiMendelowitz/applied-ml/main/adversarial-ml-toolkit/experiments/results/fgsm_examples_by_eps.png" width="480" alt="Ten CIFAR-10 images attacked with FGSM at increasing strength, from 2/255 to 16/255. The changes are barely visible, yet almost every prediction flips to a wrong class.">
</p>

### [instrumented_skills](https://github.com/AdiMendelowitz/instrumented_skills): Claude Code skills with memory

Skills I built so that repeated work on the same file carries over between sessions. Each one logs its state outside the conversation and reads it back before acting, and the [blog series](https://blog.adimendelowitz.dev/skills/intro.html) explains the reasoning behind each.

```mermaid
flowchart LR
    A[Read the log] --> B[Do the work]
    B --> C[Update the log]
    C -. next session .-> A
```

## Background

After a B.Sc. in Mathematics, I spent six years in production ML, working with clinical data at GE Healthcare and leading the fleet data team at SolarEdge, where our monitoring and root-cause analysis fed decisions about which device faults to fix and how to roll the fixes out.

Tools I use most: Python, SQL, PyTorch, scikit-learn, statsmodels, Databricks and AWS.
