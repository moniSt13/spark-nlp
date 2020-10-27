---
layout: model
title: Ner DL Model Events
author: John Snow Labs
name: ner_events_clinical
class: NerDLModel
language: en
repository: clinical/models
date: 2020-08-18
tags: [clinical,ner,en]
article_header:
   type: cover
use_language_switcher: "Python-Scala-Java"
---

{:.h2_title}
## Description
Named Entity recognition annotator allows for a generic model to be trained by utilizing a deep learning algorithm (Char CNNs - BiLSTM - CRF - word embeddings) inspired on a former state of the art model for NER: Chiu & Nicols, Named Entity Recognition with Bidirectional LSTM,CNN.
Pretrained named entity recognition deep learning model for clinical events.

## Predicted Entities 
CLINICAL_DEPT, DATE, DURATION, EVIDENTIAL, FREQUENCY, OCCURRENCE, PROBLEM, TEST, TIME, TREATMENT

{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
[Open in Colab](https://colab.research.google.com/github/JohnSnowLabs/spark-nlp-workshop/blob/master/tutorials/Certification_Trainings/Healthcare/1.Clinical_Named_Entity_Recognition_Model.ipynb){:.button.button-orange.button-orange-trans.co.button-icon}[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/clinical/models/ner_events_clinical_en_2.5.5_2.4_1597775531760.zip){:.button.button-orange.button-orange-trans.arr.button-icon}
{:.h2_title}
## How to use 
<div class="tabs-box" markdown="1">

{% include programmingLanguageSelectScalaPython.html %}

```python
model = NerDLModel.pretrained("ner_events_clinical","en","clinical/models")\
	.setInputCols("sentence","token","word_embeddings")\
	.setOutputCol("ner")
```

```scala
val model = NerDLModel.pretrained("ner_events_clinical","en","clinical/models")
	.setInputCols("sentence","token","word_embeddings")
	.setOutputCol("ner")
```
</div>

{:.model-param}
## Model Information

{:.table-model}
|----------------|----------------------------------|
| Name:           | ner_events_clinical              |
| Type:    | NerDLModel                       |
| Compatibility:  | Spark NLP 2.5.0+                            |
| License:        | Licensed                         |
|Edition:|Official|                       |
|Input labels:         | [sentence, token, word_embeddings] |
|Output labels:        | [ner]                              |
| Language:       | en                               |
| Case sensitive: | False                            |
| Dependencies:  | embeddings_clinical              |

{:.h2_title}
## Data Source
Trained on i2b2 events data with `clinical_embeddings`
https://portal.dbmi.hms.harvard.edu/projects/n2c2-nlp/