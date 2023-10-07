# KoMultiText
### Korean Multi-task Dataset for Classifying Biased Speech in Real-World Online Services
* This repository provides Korean Multi-task Text Dataset and PyTorch implementations for classifacation models.
* This work is presented at arXiv
<p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/model.png" width=90%/></p>

## Author
[Dasol Choi](https://github.com/Dasol-Choi), [Donbin Na](https://github.com/ndb796), [Jooyoung Song](https://github.com/Song-Joo-Young)


## Abstract

> The anonymous nature of online services often leads to the presence of biased and harmful language, posing challenges to maintaining the health of online communities. This phenomenon is especially relevant in South Korea, where large-scale hate speech detection algorithms have not yet been broadly explored. In this paper, we introduce a new comprehensive, large-scale dataset collected from a well-known South Korean SNS platform. Our proposed dataset provides annotations including **(1) Preferences**, **(2) Profanities**, and **(3) Nine types of Bias** for the text samples, enabling multi-task learning for simultaneous classification of user-generated texts. Leveraging state-of-the-art BERT-based language models, our approach surpasses human-level accuracy across diverse classification tasks, as measured by various metrics.


## Source Codes

|                          | RoBERTa | KR-BERT | KoELECTRA | KoBigBird |
|--------------------------|------------------|------------------|--------------------|--------------------|
| Multi-task               | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/multi_task_models/RoBERTa_multi_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/multi_task_models/KRBERT_multi_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/multi_task_models/KoELECTRA_multi_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/multi_task_models/KoBIGBIRD_multi_task.ipynb) |
| Single-task(Preference)  | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Preference/RoBERTa_preference_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Preference/KRBERT_preference_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Preference/KoELECTRA_preference_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Preference/KoBIGBIRD_preference_task.ipynb) |
| Single-task(Profanity)   | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Profanity/RoBERTa_profanity_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Profanity/KRBERT_profanity_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Profanity/KoELECTRA_profanity_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Profanity/KoBIGBIRD_profanity_task.ipynb) |
| Single-task(Bias)        | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Bias/RoBERTa_preference_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Bias/KRBERT_bias_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Bias/KoELECTRA_bias_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/single_task_models/Bias/KoBIGBIRD_bias_task.ipynb) |


## Dataset
sourced from a forum, "Real-time Best Gallery", of [DC Inside](https://www.dcinside.com/), a well-known online community in South Korea
* Labeled Dataset : Train Dataset (38,361 comments/5MB), Test Dataset (2,000 comments/286KB)
* Unlabeled Dataset (110,000 comments/11.5MD)
* [Download Dataset](https://drive.google.com/drive/folders/1E1xFJyWeOzfAmAwoeX3LpQCVkIgwUSSU?usp=sharing)
 <p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/dataset_configuration.png" width=70%/></p>
 <p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/dataset_example.png" width=90%/></p>

  
## Models Performance
* The overall classification performance for both single-task and multi-task settings including the Preference, Profanity, and Bias tasks.
* The AUROC and PRROC for the Bias task represent the average values across all biases. Detailed AUROC, PRROC, and F1-scores for each bias type are available in our paper.
* [Download Models](https://drive.google.com/drive/folders/1MmtNrZba9_x_YpPG_ELYO6cZ9VwNMOIf?usp=drive_link)
<p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/performance.png" width=75%/></p>

## Citation
