# BERT Shortcut Learning in Scientific Fact-Verification Tasks

> Aarti Lad · Arya Wadhwani · Diya Saraf · Neha Thomas | CSCI 567

## Code

All code is available in the folders under the dataset name

## Repository Structure

```
CSCI567_project/
├── FEVER/
│   ├── Bert_fever.ipynb          # CLIMATE-FEVER baseline training & evaluation
│   └── bert_future_works.ipynb   # CLIMATE-FEVER diagnostic experiments (FW1–FW5)
├── Healthver/
│   └── HealthVer_Model.ipynb     # HealthVer training & all diagnostic experiments
├── PubHealth/
│   ├── PubHealth.ipynb                    # PubHealth baseline training & evaluation
│   └── PubHealth_bert_future_works.ipynb  # PubHealth diagnostic experiments (FW1–FW5)
└── SciClaimHunt/
    └── SciClaimHunt_with_FW.ipynb  # SciClaimHunt training & diagnostic experiments
```

## Datasets

We use the following publicly available datasets. No data is included in this repository.

| Folder | Dataset | Domain | Labels | Link |
|---|---|---|---|---|
| `FEVER/` | CLIMATE-FEVER | Climate science | SUPPORTS / REFUTES / NOT ENOUGH INFO | https://huggingface.co/datasets/tdiggelm/climate_fever |
| `Healthver/` | HealthVer | Health claims | SUPPORTS / REFUTES / NEUTRAL | https://github.com/sarrouti/HealthVer |
| `PubHealth/` | PubHealth | Public health | SUPPORTS / REFUTES / NEUTRAL / MIXTURE / UNPROVEN | https://github.com/neemakot/Health-Fact-Checking |
| `SciClaimHunt/` | SciClaimHunt | Scientific papers | POSITIVE / NEGATIVE | https://huggingface.co/datasets/AnshulS/dataset_for_scicllaimhunt |

## Reproducing Results

Run each notebook top to bottom. All datasets are loaded automatically from HuggingFace or from local CSVs as noted below.

**CLIMATE-FEVER** (`FEVER/`)
```
Bert_fever.ipynb         — baseline fine-tuning, per-class F1, temperature calibration
bert_future_works.ipynb  — FW1: Synonym Swap, FW2: Attention Masking,
                           FW3: Probe Classifier, FW4: NEI Deep-Dive, FW5: Error Analysis
Dataset loaded automatically via: load_dataset("tdiggelm/climate_fever")
```

**HealthVer** (`Healthver/`)
```
HealthVer_Model.ipynb    — baseline training, synonym swap, attention masking,
                           probe classifier, NEI deep-dive, error analysis
Dataset: place healthver_train.csv and healthver_dev.csv in ./data/
         Download from https://github.com/sarrouti/HealthVer
```

**PubHealth** (`PubHealth/`)
```
PubHealth.ipynb                   — baseline fine-tuning, per-class F1, temperature calibration
PubHealth_bert_future_works.ipynb — FW1: Synonym Swap, FW2: Attention Masking,
                                    FW3: Probe Classifier, FW4: NEI Deep-Dive, FW5: Error Analysis
Dataset loaded automatically via: load_dataset("neemakot/Health-Fact-Checking")
  (or place train.tsv / dev.tsv in ./data/ if loading locally)
```

**SciClaimHunt** (`SciClaimHunt/`)
```
SciClaimHunt_with_FW.ipynb  — baseline training with paper-level split,
                               temperature calibration, all diagnostic experiments
Dataset loaded automatically via: load_dataset("AnshulS/dataset_for_scicllaimhunt")
```
