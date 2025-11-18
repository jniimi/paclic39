# Reference Points in LLM Sentiment Analysis: The Role of Structured Context

[![PACLIC 39](https://img.shields.io/badge/PACLIC-39-blue)](https://paclic39.github.io/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

This repository accompanies the paper presented at **PACLIC 39 (The 39th Pacific Asia Conference on Language, Information and Computation)**.

## 📄 Paper Information

**Title:** Reference Points in LLM Sentiment Analysis: The Role of Structured Context

**Author:** Junichiro Niimi
Faculty of Business Management, Meijo University
RIKEN AIP

**Published in:** Proceedings of The 39th Pacific Asia Conference on Language, Information and Computation (PACLIC 39), 2025

**Contact:** jniimi@meijo-u.ac.jp

---

## 📋 Abstract

Large language models (LLMs) are now widely used across many fields, including marketing research. While most NLP studies classify sentiment from review text alone, marketing theories such as prospect theory and expectation-disconfirmation theory point out that customer evaluations are shaped not only by the actual experience but also by additional reference points.

This study investigates how the content and format of supplementary information affect sentiment analysis using LLMs. We compare natural language (NL) and JSON-formatted prompts using a lightweight 3B parameter model suitable for practical marketing applications.

**Key Findings:**
- JSON prompt with additional information outperforms all baselines without fine-tuning
- Macro-F1 rises by 1.6% and 4% for Restaurant and Nightlife categories
- RMSE falls by 16% and 9.1% respectively
- Performance gains stem from genuine contextual reasoning rather than label proxying

---

## 📊 Research Questions

This study addresses four key research questions:

1. **RQ1 (Reference-point utilization):** Does supplying user- and business-average ratings help an LLM classify sentiment more accurately?
2. **RQ2 (Prompt format):** Does the prompt format affect model performance when the same information is presented in different structures?
3. **RQ3 (Proxy effect):** If supplying reference points improves accuracy, is it due to their implicit encoding of ground-truth labels?
4. **RQ4 (Reference interactions):** How do interactions between multiple reference points affect prediction accuracy?

---

## 🎯 Main Contributions

- **Theoretical Integration:** Bridges marketing theory (prospect theory, expectation-disconfirmation theory) with LLM-based sentiment analysis
- **Structured Prompting:** Demonstrates that JSON-formatted prompts enable smaller models (3B parameters) to achieve competitive performance
- **Practical Deployment:** Shows feasibility for resource-constrained edge devices without fine-tuning
- **Reference Point Analysis:** Confirms that performance gains stem from contextual reasoning, not label proxying

---

## 📁 Repository Structure

This repository provides supplementary information for the paper. **Note:** Source code is not publicly available in this repository.

```
paclic39/
├── README.md                 # This file
└── PACLIC39-cameraready.pdf # Paper (if available)
```

---

## 🔬 Methodology Overview

### Model
- **Base Model:** Llama 3.2 (3B parameters, instruction-tuned)
- **Approach:** Zero/one-shot learning without fine-tuning
- **Prompting Strategies:** Natural Language (NL) vs. JSON-formatted prompts

### Dataset
- **Source:** Yelp Open Dataset
- **Categories:** Restaurant and Nightlife
- **Sample Size:** 500 unique user-business pairs per category
- **Language:** English

### Supplementary Information
- **U (User Average):** Mean rating of user's past reviews
- **B (Business Average):** Mean rating the business has received
- **O (Other):** Contextual factors (restaurant name, operating hours, etc.)

### Evaluation Metrics
- **Macro-F1 Score:** Classification accuracy
- **RMSE:** Regression error on ordinal scale (1-5 stars)

---

## 📈 Key Results

### Study 1: Impact of Reference Points and Display Methods

**Restaurant Dataset:**
- JSON-UBO: Macro-F1 = 0.612, RMSE = 0.564
- Best improvement over baseline: +4.3% F1, -16.4% RMSE

**Nightlife Dataset:**
- JSON-UBO: Macro-F1 = 0.635, RMSE = 0.597
- Best improvement over baseline: +20.7% F1, -15.8% RMSE

### Study 2: Relationship with Expectation
- Performance improves when ratings deviate from expectations
- Confirms reference points are not mere label proxies

### Study 3: Error Analysis
- Highest accuracy when user average (UA) = 5
- Better performance when reference points align (UA ≈ BA)
- Conflicting references indicate inherently challenging cases

---

## 💡 Practical Implications

1. **Immediate Deployment:** No fine-tuning required - companies can use existing databases with JSON prompts
2. **Edge Computing:** 3B parameter model enables on-device processing with privacy preservation
3. **Adaptive Inference:** Route simple cases to lightweight models, complex cases to larger models
4. **Energy Efficiency:** Computational resources allocated based on prediction difficulty

---

## 🔍 Theoretical Background

### Prospect Theory
Consumers evaluate services by comparing actual experience to pre-established reference points (Kahneman & Tversky, 2013).

### Expectation-Disconfirmation Theory (EDT)
- **Absolute Evaluation:** Whether perceived quality meets a fixed standard
- **Relative Evaluation:** Based on comparing prior expectations with perceived quality (Oliver, 1980)

---

## ⚠️ Limitations

1. **Single Model Architecture:** Experiments conducted only with Llama-3.2-3B-Instruct
2. **Limited Domain Coverage:** Only Restaurant and Nightlife categories from Yelp dataset
3. **Language:** English reviews only
4. **Psychological Validation:** Theoretical mechanisms not empirically tested through psychological experiments
5. **Baseline Comparisons:** No comparison with post-hoc calibration methods

---

## 🙏 Acknowledgments

This study is supported by JSPS KAKENHI (Grant Number: 24K16472).

We are grateful to the anonymous reviewers for their insightful comments.

---

## 📖 Citation

If you use this work in your research, please cite:

```bibtex
@inproceedings{niimi2025reference,
  title={Reference Points in LLM Sentiment Analysis: The Role of Structured Context},
  author={Niimi, Junichiro},
  booktitle={Proceedings of The 39th Pacific Asia Conference on Language, Information and Computation (PACLIC 39)},
  year={2025},
  organization={PACLIC}
}
```

**Plain text citation:**
```
J. Niimi (2025) "Reference Points in LLM Sentiment Analysis: The Role of Structured Context",
Proceedings of The 39th Pacific Asia Conference on Language, Information and Computation (PACLIC 39).
```

---

## 📧 Contact

For questions or collaboration inquiries, please contact:

**Junichiro Niimi**
Faculty of Business Management, Meijo University
RIKEN AIP
Email: jniimi@meijo-u.ac.jp

---

## 📜 License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

You are free to:
- **Share:** Copy and redistribute the material in any medium or format
- **Adapt:** Remix, transform, and build upon the material for any purpose, even commercially

Under the following terms:
- **Attribution:** You must give appropriate credit, provide a link to the license, and indicate if changes were made

---

## 🔗 Related Resources

- [PACLIC 39 Conference Website](https://paclic39.github.io/)
- [Yelp Open Dataset](https://www.yelp.com/dataset)
- [Llama 3.2 Model Card](https://huggingface.co/meta-llama/Llama-3.2-3B-Instruct)

---

**Note:** This repository is intended for academic and research purposes. Source code is not publicly available. For specific implementation details, please refer to the paper or contact the author.
