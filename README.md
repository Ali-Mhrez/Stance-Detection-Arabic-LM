# Repository of the paper: [Evaluating the Performance of Arabic Language Models on the Task of Stance Detection Towards Fake News](https://journal.homs-univ.edu.sy/index.php/Engineering/article/view/5120), Full text: [pages 83-106](https://journal.homs-univ.edu.sy/index.php/Engineering/issue/view/789/721).

This repository contains the code for a research paper that explores the performance of all Arabic language models on the task of stance detection in the context of fake news. The task involves classifying the relationship between a news article's body text and its headline into one of four categories: agree, disagree, discuss, or unrelated. The fine-tuned models include ARBERT, ARABERT, ARAELECTRA, and others.

## Goal and Background
Despite the growing number of powerful transformer-based models for the Arabic language, their application to a critical task like fake news stance detection remains largely unexplored. Currently, there is a significant lack of research evaluating the performance of these models, such as AraBERT, ARBERT, and AraELECTRA, on this specific task. This absence of a clear benchmark hinders progress in the field and makes it difficult to understand the strengths and weaknesses of these models. Furthermore, there are no existing studies that systematically analyze the impact of various design and training characteristics on their effectiveness.

Our primary goal is to address this research gap by providing a comprehensive analysis of state-of-the-art Arabic transformers. We aim to:
1. **Evaluate Performance:** Shed light on the effectiveness of a wide range of modern Arabic transformers by fine-tuning and evaluating them for the task of fake news stance detection.
2. **Analyze Design Characteristics:** Conduct a comparative study of the models' core characteristics, including their vocabulary size, training tasks, training data, and final model size, to identify the settings most suitable for this specific task.
3. **Contribute a Benchmark:** Provide a clear benchmark and detailed error analysis that will enable future researchers to develop more effective transformers tailored for Arabic stance detection.

This study makes the following contributions:
1. **Systematic Performance Evaluation:** We evaluate the performance of all previously unstudied Arabic transformers on the stance detection task.
2. **Impact of Design Choices:** We compare the design and development settings of these transformers and analyze their impact on performance.
3. **Error Analysis:** We highlight the models' weaknesses by conducting a detailed analysis of their classification errors.

## Dataset
The [AraStance](https://aclanthology.org/2021.nlp4if-1.9/) dataset includes article bodies, headlines, and a corresponding class label. The label indicates the stance of the article body with respect to the headline. The article body can either Agree (AGR) or Disagree (DSG) with the headline, it can Discuss (DSC) it or be completely Unrelated (UNR).
| Data Source | Data Type | Instances | AGR | DSG | DSC | UNR |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| [paper repo](https://github.com/Tariq60/arastance) | News articles | 4,063 | 25.1% | 11.0% | 9.5% | 54.3% |

## Data Preprocessing
The dataset is already divided into: Training, Validation, Testing sets.  
No Special preprocessing was conducted except tokenization using the default tokenizer of each model.

## Models:

| Model | Vocabulary size | Training Tasks | Training Data | Data Size | Parameters |
|:---|:---:|:---:|:---:|:---:|:---:|
| [ARA-ELECTRA](https://aclanthology.org/2021.wanlp-1.20/) | 64K | RTD | MSA | 77GB | 136M |
| [AR-BERT](https://aclanthology.org/2021.acl-long.551/) | 100K | MLM | MSA | 61GB | 163M |
| [MAR-BERT](https://aclanthology.org/2021.acl-long.551/) | 100K | MLM | MSA+Dialect | 128GB | 163M |
| [QARIB](https://aclanthology.org/2020.wanlp-1.21/) | 64K | MLM | MSA+Dialect | 25GB | 135M |
| [MDA-BERT](https://aclanthology.org/2020.wanlp-1.10/) | 32K | MLM | MSA+Dialect | 105GB | 110M |
| [ARABIC-BERT](https://aclanthology.org/2020.semeval-1.271/) | 32K | MLM | Mostly MSA | 95GB | 11M,42M,110M,340M |
| [ARA-BERT](https://aclanthology.org/2020.osact-1.2/) | 64K | MLM+NSP | MSA | 24GB | 135M |
| [GIGA-BERT](https://aclanthology.org/2020.emnlp-main.382/) | 50K | MLM | MSA | - | 125M |
| [ARABIC-ALBERT](https://github.com/KUIS-AI/Arabic-ALBERT) | 30K | MLM+SOP | Mostly MSA | - | 12M,18M,60M |

## Key Results

Our research yielded several key findings regarding the use of Arabic transformers for stance detection:
- **Model Performance:** ARA-BERT consistently outperformed all other models, establishing a new benchmark for this task.
- **Pre-training Objective:** The masked language model (MLM) pre-training objective proved to be more effective for this task than the retrieval substitution detection (RTD) task.
- **Language Variety:** Models trained on Modern Standard Arabic (MSA) demonstrated superior performance compared to those trained on dialectal Arabic.
- **Vocabulary Size:** Increasing the model's vocabulary size beyond approximately 64,000 units did not lead to a significant improvement in performance.
- **Development Focus:** Our findings suggest that for building effective Arabic stance detection models, researchers should prioritize the training tasks and the type of training data over simply increasing the amount of training data or the size of the vocabulary.

## Requirements

- Python 3.10.12
- NumPy 1.26.4
- PyTorch 2.5.1+cu121
- Transformers 4.46.3
- Scikit-learn 1.5.2
- arabert 1.0.1

## Citation
```bash
@article{amhrez-alm,
title = {Evaluating the Performance of Arabic Language Models on the Task of Stance Detection Towards Fake News},
journal = {Journal of Homs Univeristy},
Series = {Mechanical, Electrical and Information Engineering Sciences Series},
volume = {46},
number = {5},
pages = {83--106},
year = {2024},
url = {https://journal.homs-univ.edu.sy/index.php/Engineering/article/view/5120},
author = {Mhrez, ali; Ramadan, Wassim; Abo Saleh, Naser},
keywords = {stance  detection, fake news, Arabic language models, natural language processing},
}
```
