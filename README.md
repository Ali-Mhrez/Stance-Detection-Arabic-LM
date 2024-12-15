# Stance Detection Using Arabic Large Language Models

This repository contains codes to fine-tune several Arabic language models on the task of stance detection.

## Models:

* **ArBERT**.
* **AraBERT**
* **ArabicBERT**.
* **AraElectra**
* **GigaBERT**.
* **Qarib**.
* **ALBERT**.

## Dataset:
The test fine-tuning were conducted on Google Colab (T4 GPU) using a AraStance (Alhindi et al., [2021](https://aclanthology.org/2021.nlp4if-1.9/)) dataset.

## Evaluation Metrics:

* **Accuracy:** the ratio of the number of correct predictions to the total number of predictions.
* **F1-Score:** the harmonic mean of precision and recall.
* **Macro F1-score:** average of per-class f1-scores.

## Results and Analysis:

The following results are based on a single training run. This clearly indicates that the reported performance might vary due to the inherent randomness in the training process.

### Validation Results

| Model | Accuracy | Agree | Disagree | Discuss | Unrelated | Macro f1-score |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| ArBERT | 0.849 | 0.837 | 0.806 | **0.596** | **0.924** | 0.791 |
| AraBERT | **0.863** | 0.870 | **0.848** | 0.559 | 0.923 | **0.800** |
| ArabicBERT | 0.837 | 0.829 | 0.761 | 0.558 | 0.915 | 0.766 |
| AraElectra | 0.801 | 0.789 | 0.738 | 0.283 | 0.905 | 0.679 |
| GigaBERT | 0.854 | **0.882** | 0.788 | 0.581 | 0.925 | 0.794 |
| Qarib | 0.786 | 0.803 | 0.755 | 0.506 | 0.870 | 0.734 |
| ALBERT | 0.842 | 0.844 | 0.764 | 0.580 | 0.922 | 0.777 |

### Testing Results

| Model | Accuracy | Agree | Disagree | Discuss | Unrelated | Macro f1-score |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| ArBERT | **0.873** | **0.875** | 0.764 | 0.548 | **0.946** | **0.783** |
| AraBERT | 0.870 | 0.860 | **0.800** | 0.505 | 0.940 | 0.776 |
| ArabicBERT | 0.854 | 0.844 | 0.769 | 0.492 | 0.931 | 0.759 |
| AraElectra | 0.819 | 0.774 | 0.695 | 0.200 | 0.930 | 0.650 |
| GigaBERT | 0.865 | 0.873 | 0.777 | 0.557 | 0.936 | 0.786 |
| Qarib | 0.803 | 0.786 | 0.763 | 0.466 | 0.892 | 0.727 |
| ALBERT | 0.856 | 0.837 | 0.777 | **0.560** | 0.930 | 0.776 |

## Future Work:

1. **Multiple Runs:** To obtain more robust results, consider running multiple training sessions with different random seeds and averaging the performance across the runs.
2. **Investigate data augmentation techniques:** Explore techniques to improve data diversity and model robustness.
3. **Fine-tune on larger and more diverse datasets:** Train the models on larger and more diverse datasets to enhance their generalizability.

In addition, it is possible to further improve the performance of the models on this classification task by carefully considering the following:

4. **Class Imbalance**: Techniques like class weighting or oversampling could be explored to address the class imbalance in the dataset.
5. **Hyperparameter Tuning**: Conduct a thorough hyperparameter search to optimize the performance of each model.

## Software/Libraries:

- Python 3.10.12
- NumPy 1.26.4
- PyTorch 2.5.1+cu121
- Transformers 4.46.3
- Scikit-learn 1.5.2
- arabert 1.0.1
