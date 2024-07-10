# Domain-Knowledge-into-PLMs-for-EBM (Accepted into AIME 2024 Main Conference)

### Table of Contents
- [Abstract](#features)
- [Methodology](#installation)
- [Prerequisites](#usage)
- [SR Train/Test Dataset](#visualizing-attacks)
- [Models](#generating-adversarial-images)
- [Limitation](#limitation)


### Abstract

Evidence-based medicine (EBM) represents a cornerstone in medical research, guiding policy and decision-making. However, the robust steps involved in EBM, particularly in the abstract screening stage, present significant challenges to researchers. Numerous attempts to automate this stage with pre-trained language models (PLMs) are often hindered by domain-specificity, particularly in EBMs involving animals and humans. Thus, this research introduces a state-of-the-art (SOTA) transfer learning approach to enhance abstract screening by incorporating domain knowledge into PLMs without altering their base weights. This is achieved by integrating small neural networks, referred to as knowledge layers, within the PLM architecture. These knowledge layers are trained on key domain knowledge pertinent to EBM, PICO entities, PubmedQA, and the BioASQ 7B biomedical Q\&A benchmark datasets. Furthermore, the study explores a fusion method to combine these trained knowledge layers, thereby leveraging multiple domain knowledge sources. Evaluation of the proposed method on four highly imbalanced EBM abstract screening datasets demonstrates its effectiveness in accelerating the screening process and surpassing the performance of strong baseline PLMs.


For more details, please check the latest version of the paper


### Methodology

![Image Alt text](dual_encoder_naacl.PNG)


###  Prerequisites
``` bash
- Python 3.6
- sklearn
- spacy
- torch
- transformers
```

### Spanish SR Train/Test Dataset

- Training Dataset: Spanish abstracts from 2009 to 2023 were collected from the [LILACS](https://lilacs.bvsalud.org/en/) database. To obtain abstract-queries pair for training, the titles of biomedical abstracts indexed and collected from the [LILACS](https://lilacs.bvsalud.org/en/) database were converted into questions/queries.


- Testing Dataset: To evaluate the performance of the investigated model, we used three biomedical human annotated Spanish SR case studies: **SB**: [Oral health and obesity in Mexico (salud bucal y obesidad en México)](https://academic.oup.com/nutritionreviews/article/80/6/1694/6402007?login=false), **SM**: [Mental health and obesity in Mexico (salud mental y obesidad en México)](https://academic.oup.com/nutritionreviews/article/81/6/658/6717764?login=false), and **PO**: [Obesity prevention in Mexican children (prevención de obesidad en ninos mexicanos)](https://link.springer.com/article/10.1007/s11121-021-01316-6).

| **Dataset**          | **Research Question (Spanish)**                                                                              | **Papers retrieved (LILACS)** | **Total Papers** | **Total Included** | **Included papers (LILACS)** |
|----------------------|--------------------------------------------------------------------------------------------------------------|-------------------------------|------------------|--------------------|------------------------------|
| Oral Health (SB)     | ¿Existe asociación entre obesidad o sobrepeso y mala salud bucal en niños y adolescentes mexicanos?           | 73                            | 9828             | 18                 | 3                            |
| Mental Health (SM)   | ¿Cuál es la asociación entre la obesidad o el sobrepeso y los problemas de salud mental entre los niños y adolescentes mexicanos? | 35                            | 1074             | 16                 | 6                            |
| Obesity Prevention (PO) | ¿Cuál es la efectividad de las intervenciones de prevención de la obesidad entre los niños mexicanos?        | 20                            | 9828             | 29                 | 2                            |



### Models

- BM25 
- Dual encoder PLM (mBERT, BETO, XLM-R Galén and bsc-bio-ehr-es)
- Cross attention re-ranker model 





