# Prompt Injection Detection System

**Undergraduate Thesis Project**  
Building an AI system to detect prompt injection attacks on Large Language Models (LLMs)

---

## 🎯 Project Overview

This repository contains my undergraduate thesis work on developing machine learning models to detect prompt injection attacks. Prompt injection is a critical security vulnerability in LLM-integrated applications where malicious inputs can manipulate model behavior.

---

## 📊 Dataset

**PromptShield Dataset**
- Source: [hendzh/PromptShield](https://huggingface.co/datasets/hendzh/PromptShield) on Hugging Face
- Size: ~42,500 labeled prompts
- Classes: Legitimate (0) vs Injection (1)
- Balance: 50/50 split

Reference: Jacob et al. (2025) - PromptShield: Deployable Detection for Prompt Injection Attacks

---

## 🧪 Experiments

### Experiment 1: DistilBERT Baseline ❌
- **Model:** DistilBERT-base-uncased (~66M parameters)
- **Result:** 79% test accuracy, poor generalization
- **Status:** Failed - model couldn't detect simple injections
- **Report:** [EXPERIMENT_1_REPORT.md](EXPERIMENT_1_REPORT.md)

### Experiment 2: BERT-base (In Progress) 🚧
- **Model:** BERT-base-uncased (~110M parameters)
- **Status:** Currently training
- **Expected Improvement:** Better capacity for complex patterns

---

## 🛠️ Tech Stack

- **Framework:** PyTorch + Hugging Face Transformers
- **Platform:** Google Colab (free GPU)
- **Languages:** Python 3.10+
- **Key Libraries:** transformers, datasets, scikit-learn, torch

---

## 📁 Repository Structure

```
prompt-injection-detector/
│
├── experiments/
│   ├── experiment_1_distilbert/
│   │   ├── notebook.ipynb
│   │   └── EXPERIMENT_1_REPORT.md
│   └── experiment_2_bert/
│       └── notebook.ipynb
│
├── data/
│   └── (Dataset loaded from Hugging Face)
│
├── models/
│   └── saved_models/
│
├── README.md
└── requirements.txt
```

---

## 🚀 Quick Start

### Installation

```bash
pip install -r requirements.txt
```

### Load Dataset

```python
from datasets import load_dataset
dataset = load_dataset("hendzh/PromptShield")
```

### Run Training

Open the Jupyter notebook for the desired experiment and run cells sequentially.

---

## 📈 Results Summary

| Experiment | Model | Test Accuracy | Injection Recall | Status |
|-----------|-------|---------------|------------------|---------|
| 1 | DistilBERT | 79.3% | 68% | ❌ Failed |
| 2 | BERT-base | TBD | TBD | 🚧 In Progress |

---

## 🎓 Research Questions

1. What model architectures are most effective for prompt injection detection?
2. How does model size impact generalization to unseen injection patterns?
3. Can we achieve production-ready performance (>95% accuracy, <5% false negatives)?
4. What techniques help prevent overfitting while maintaining high recall?

---

## 📚 References

1. Jacob, D., Alzahrani, H., Hu, Z., Alomair, B., & Wagner, D. (2025). *PromptShield: Deployable Detection for Prompt Injection Attacks*. arXiv:2501.15145

2. Devlin, J., et al. (2019). *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding*

3. Sanh, V., et al. (2019). *DistilBERT, a distilled version of BERT*

---

## 🤝 Contributing

This is an undergraduate thesis project. Feedback and suggestions are welcome via issues!

---

## 📧 Contact

For questions about this research, please open an issue in this repository.

---

## 📄 License

This project is for academic research purposes.

---

**Last Updated:** November 1, 2025  
**Status:** Active Development
