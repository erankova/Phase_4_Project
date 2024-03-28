# Natural Language Processing Medical Question & Question Type

**Data Sciencist:** Elina Rankova

<div style="width: 100%; text-align: center;">
  <img src="https://altheia.com/wp-content/uploads/2020/12/0KbmpXTpCCIt1TR1B-1280x720.png" width="720" height="450" style="margin: 0 auto;"/>
</div>

<u>image source</u>: <a href="https://altheia.com/recommended-tools-for-data-scientists-in-the-medical-field/">Altheia; Recommended Tools for Data Scientists in the Medical Field</a>

## Business Problem and Understanding

**Stakeholders:** Healing Hearts Partners, Lead Receptionist, Lead Nurse, Lead Medical Assistant

Healing Hearts is growing and is noticing that patients are not recieving response to common questions regarding specific diseases in a timely manner. They are interseted in automating the Q&A process for both patients and the front desk staff who have a hard time distinguishing where to direct questions.

For Phase 1 of this Natural Language Processing (NLP) task, we will be classifying the questions based on question type, aiming to predict the question type of questions being asked of reception.

**The goal:** Create classification model that predicts question type from which reception can determine who is best equiped to answer patient, improving productivity and patient satisfaction.

## Data Understanding and Exploration

For this the <a href="https://www.kaggle.com/datasets/thedevastator/comprehensive-medical-q-a-dataset/code">Comprehensive Medical Q&A Dataset</a> sourced from Kaggle.

Our target will the be `qtype` or question type and we will try to match the `Question` column to be able to advice on appropriate next steps accoridng to the type of question being asked. Questions consist of common inquiries about specific diseases. 

### Observations
- No missingness to take care of
- 16407 records
- 16 total classes

**Question Example per Label** 
susceptibility :  Who is at risk for Lymphocytic Choriomeningitis (LCM)?
symptoms :  What are the symptoms of Lymphocytic Choriomeningitis (LCM)?
exams and tests :  How to diagnose Lymphocytic Choriomeningitis (LCM)?
treatment :  What are the treatments for Lymphocytic Choriomeningitis (LCM)?
prevention :  How to prevent Lymphocytic Choriomeningitis (LCM)?
information :  What is (are) Parasites - Cysticercosis?
frequency :  how common are these diseases for Marine Toxins?
complications :  are there complications from botulism?
causes :  What causes Chronic Fatigue Syndrome (CFS)?
research :  what research is being done for Tuberculosis (TB)?
outlook :  What is the outlook for Striatonigral Degeneration?
considerations :  What to do for Lactose Intolerance?
inheritance :  Is Ovarian Epithelial, Fallopian Tube, and Primary Peritoneal Cancer inherited?
stages :  What are the stages of Ovarian Epithelial, Fallopian Tube, and Primary Peritoneal Cancer?
genetic changes :  What are the genetic changes related to Chronic Myelogenous Leukemia?
support groups :  Where to find support for people with Alcohol Use and Older Adults?

**Class Imbalance**

Since we have some question types that have very few instances, we will have to drop that row before spliting our data if we want to keep class proportions. We will also have to consider our class imbalance when creating our models.

We can also use `LabelEncoder` to transform this variable before the train test split if we choose.

**Note:** There class `support groups` only has one record, if we plan to keep our class proportions when we plit our data, we will have to drop this class

[Class Count Chart]

### Preprocess Analysis

First, we should take a look at what the word frequency looks like before cleaning our data for things like stopwords and punctuation. It looks like we have a lot of stop words as well as other words that typically would be meaningful but are not in our medical context.

[Top 20 Raw Tolkens.png]
![Top 20 Raw Tolkens](https://github.com/erankova/Phase_4_Project/assets/155934070/611af996-01b0-4f38-9cf7-26414e6ec83b)



















