# KoMultiText
[![arXiv](https://img.shields.io/badge/arXiv-2310.04313-b31b1b.svg)](https://arxiv.org/abs/2310.04313)
### Korean Multi-task Dataset for Classifying Biased Speech in Real-World Online Services
> Paper Title: Large-Scale Korean Text Dataset for Classifying Biased Speech in Real-World Online Services

* This repository provides Korean Multi-task Text Dataset and PyTorch implementations for classification models.
* <b>(News)</b> This work is accepted to the <b>NeurIPS 2023</b> workshop on [Socially Responsible Language Modelling Research (SoLaR)](https://solar-neurips.github.io/).

<p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/model.png" width=90%/></p>

## Authors
[Dasol Choi](https://github.com/Dasol-Choi), [Jooyoung Song](https://github.com/Song-Joo-Young), [Eunsun Lee](https://github.com/eunsun111), [Jinwoo Seo](https://github.com/dukong1),  [Heejune Park](https://github.com/heejunepark), [Donbin Na](https://github.com/ndb796), 


## Abstract

> The anonymous nature of online services often leads to the presence of biased and harmful language, posing challenges to maintaining the health of online communities. This phenomenon is especially relevant in South Korea, where large-scale hate speech detection algorithms have not yet been broadly explored. In this paper, we introduce a new comprehensive, large-scale dataset collected from a well-known South Korean SNS platform. Our proposed dataset provides annotations including **(1) Preferences**, **(2) Profanities**, and **(3) Nine types of Bias** for the text samples, enabling multi-task learning for simultaneous classification of user-generated texts. Leveraging state-of-the-art BERT-based language models, our approach surpasses human-level accuracy across diverse classification tasks, as measured by various metrics.


## Source Codes

|                          | RoBERTa | KR-BERT | KoELECTRA | KoBigBird |
|--------------------------|------------------|------------------|--------------------|--------------------|
| Multi-task               | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/01_multi_task_models/RoBERTa_multi_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/01_multi_task_models/KRBERT_multi_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/01_multi_task_models/KoELECTRA_multi_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/01_multi_task_models/KoBIGBIRD_multi_task.ipynb) |
| Single-task(Preference)  | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Preference/RoBERTa_preference_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Preference/KRBERT_preference_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Preference/KoELECTRA_preference_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Preference/KoBIGBIRD_preference_task.ipynb) |
| Single-task(Profanity)   | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Profanity/RoBERTa_profanity_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Profanity/KRBERT_profanity_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Profanity/KoELECTRA_profanity_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Profanity/KoBIGBIRD_profanity_task.ipynb) |
| Single-task(Bias)        | [RoBERTa](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Bias/RoBERTa_bias_task.ipynb) | [KR-BERT](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Bias/KRBERT_bias_task.ipynb) | [KoELECTRA](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Bias/KoELECTRA_bias_task.ipynb) | [KoBigBird](https://github.com/Dasol-Choi/KoMultiText/blob/main/02_single_task_models/Bias/KoBIGBIRD_bias_task.ipynb) |


## Dataset
sourced from a forum, "Real-time Best Gallery", of [DC Inside](https://www.dcinside.com/), a well-known online community in South Korea

* Total 150,000 comments
  * Labeled Dataset: Train Dataset (38,361 comments/5MB), Test Dataset (2,000 comments/286KB)
  * Unlabeled Dataset (110,000 comments/11.5MD)

 <p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/dataset_configuration.png" width=70%/></p>
 <p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/dataset_example.png" width=90%/></p>

* Loading the Dataset
```python
from datasets import load_dataset

dataset = load_dataset("Dasool/KoMultiText")
print(dataset["test"][0])
```
  
## Models Performance
[Download Models](https://drive.google.com/drive/folders/1MmtNrZba9_x_YpPG_ELYO6cZ9VwNMOIf?usp=drive_link)
* The overall classification performance for both single-task and multi-task settings including the Preference, Profanity, and Bias tasks. The AUROC and PRROC for the Bias task represent the average values across all biases.
<p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/performance.png" width=70%/></p>

* Detailed AUROC, F1-score, and PRROC results for each specific bias type.
<p align="center"><img src="https://github.com/Dasol-Choi/KoMultiText/blob/main/resources/bias_task_perfomance.png" width=110%/></p>


## Citation
If this work can be useful for your research, please cite our paper:

<pre>
@misc{choi2023largescale,
      title={Large-Scale Korean Text Dataset for Classifying Biased Speech in Real-World Online Services}, 
      author={Dasol Choi and Jooyoung Song and Eunsun Lee and Jinwoo Seo and Heejune Park and Dongbin Na},
      year={2023},
      eprint={2310.04313},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
