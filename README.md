# ANCHOR-IBD: Learning Together, Data Stays Home

An interactive, scroll-driven briefing on decentralised **swarm learning** across Swedish and Norwegian IBD registries (Region Östergötland and Örebro on SWIBREG, Oslo University Hospital on NorIBD), running on **NVIDIA DGX Spark** with **NVIDIA FLARE**.

## ▶ Open the presentation

**Live, no install:** https://kanaaraman.github.io/anchor-ibd-presentation/

It works in any modern desktop or mobile browser. Scroll, or use the arrow keys.

## What is in it

15 scenes:

| Scene | What it shows |
| --- | --- |
| The problem | Why each national registry alone is too small |
| The idea | Pool the data vs a central server (FedAvg) vs swarm learning: pick one and watch what travels |
| **Live simulation** | A real swarm-learning run in your browser: three synthetic hospital cohorts, a rotating averaging hospital, a privacy-noise slider, and live scores against "each hospital alone" and the pooled ceiling |
| One round | The four steps NVIDIA FLARE's swarm workflow runs every round |
| On the Sparks | What each hospital's DGX Spark runs and sends |
| **What it predicts** | A therapy-selection explorer: describe a patient and compare the predicted chance of remission for infliximab, adalimumab, vedolizumab and ustekinumab, using the model just trained in your browser |
| The data | The three synthetic OMOP CDM cohorts and their different case mixes |
| Results | The measured PoC results by hospital and by sex |
| Rounds and privacy | The learning curve over 30 rounds and a privacy dial |
| Run it | A replay of a real run of the one-command demo |
| Rollout, status, next steps | How to deploy on Sparks, what has and has not been run, and the path to the follow-on project |

## Run locally

It is a single self-contained `index.html` with no build step. Double-click it, or serve the folder:

```bash
python -m http.server 8000
```

Google Fonts load from the internet and fall back to system fonts offline.

## Data and scope

All patients are synthetic; no real registry data is used. The in-browser simulation uses a small logistic model, so its numbers vary with each new cohort. The "Results" and "Rounds and privacy" scenes show the measured numbers from the proof-of-concept code: AUROC 0.714 for each hospital alone, 0.728 for swarm learning and 0.734 for pooled data, on 3,000 new synthetic patients per hospital, averaged over 5 training runs. The predictions are a research demonstration and must not be used for clinical decisions.

Part of the Vinnova-funded ANCHOR-IBD feasibility project (2026-00990): Region Östergötland, RISE, Örebro University, AbbVie and Oslo University Hospital.
