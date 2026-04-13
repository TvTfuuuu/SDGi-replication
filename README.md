# SDGi replication

## 1. Introduction 
I have not replicate all the experiments from the author’s articel, but rather the most essential ones.

**supervised baseline**：

- **TF-IDF and linear SVM-style multi-class classifier**
- code：`sdgi_replication.py`

This is a **partial replication**, not exact reproduction.

## 2. The paper used for reproduction
**Skrynnyk, M., Disassa, G., Krachkov, A., & DeVera, J. (2024). _SDGi Corpus: A Comprehensive Multilingual Dataset for Text Classification by Sustainable Development Goals_. Proceedings of the 2nd Symposium on NLP for Social Good.**

## 3. Data
Public datasets:

- `UNDP/sdgi-corpus`（Hugging Face）

By default, the script downloads the dataset directly from Hugging Face.

## 4. code

- `sdgi_partial_replication_minimal_cn.py`
- `requirements_sdgi_minimal_cn.txt`

## 5. Eviroment

- **Python 3.11**

Install dependencies:

```bash
pip install -r requirements_sdgi.txt
```

## 6. Run with a single command

```bash
python sdgi_replication.py
```

The default configuration is：

- `size = x`
- `language = en`

In other words, the most commonly used `sdgi-x-en` setting.

## 7. What does the script do automatically?
The script automatically performs the following steps:

1. Load the `UNDP/sdgi-corpus`
2. Use the predefined `train/test split`
3. Filter by `size` and `language`
4. Perform lightweight text pre-processing
5. Construct TF-IDF representations
6. Train a multi-label linear classifier
7. Evaluate on the test set
8. Save the results file and images

## 8. output result
An output folder will be created after execution（`sdgi_outputs/`）, including：

- `summary.json`
- `train_report.txt`
- `test_report.txt`
- `test_predictions.csv`
- `tfidf_vectorizer.joblib`
- `robust_multilabel_sgd.joblib`
- `figure_test_metrics.png`
- `figure_macro_f1_vs_paper.png`
- `figure_label_distribution.png`

