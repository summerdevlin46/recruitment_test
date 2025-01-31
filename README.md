# Recruitment Test: Extraction of scientific data and detection of bias in research articles

## Task description

We propose a possible scenario in which we want to evaluate the information in a multitude of scientific articles to find biases. The objective of this task is to find relevant information for further analysis by automatically identifying the information present and missing in the text of an example article.  

#### 1. Extract relevant information

- Studied disease condition
- Number of patients 
- Number of patients in case and control groups
- Give me the sex of the patients (if applicable) 
- Give me the origin of the patients (if applicable)

Use an LLM model to identify this information and include comments explaining the prompt engineering and reasoning used. You don't have to subscribe to openai, or any other or buying subscription for this task. A simple BERT model as placeholder would suffice for instance. The idea is to see the pipeline, not the actual results. 


#### 2. Think about the text

- Do you find that there is relevant information missing from the data we have asked for?
  I think there are two ways to interpret this question:
  ##### 1) Given the categories above, do they pull the relevant data from the article?  
	From the categories given, I had originally assumed that all the papers were going to be experimental studies. However, after setting up the pipeline and testing, I realized that many were systematic reviews, scoping reviews, or observational studies. Since these studies do not include patients, case groups, or control groups, but still contain relevant information, I had to broaden the LLM prompting to accommodate different study designs. Additionally, the category of "origin of the patient" turned out to be somewhat ambiguous because most of the studies will state where the study was conducted, which could be considered an indicator of origin, but some studies do provide demographic information for the participants. Therefore, it could be more accurate to have a category labeled "patient demographics" (or just "patient ethnicity") and "study site" to clarify the data collection.
  
  ##### 2) Is there other data from the articles that could be relevant for analysis?  
     I think there was substantial data in the articles that could have been analyzed besides those categories. For example, I saw that some studies were using both male and female participants, but did not analyze data separately, which can be problematic because it can mask important biological and social differences. Some papers provided average age of participants, socioeconomic status, disability-status, and language of the participants, and this could also be useful when studying intersectionality of these factors within sex and gender bias. Additionally, the study designs could be evaluated for their set-ups, and if they are considered inclusive designs.
---
- Can they be inferred? How?
  To capture these additional factors effectively, several approaches can be taken:  

	##### 1) Enhanced Prompt Engineering in the LLM Instruct Model 
	- Instead of a static list of categories, the LLM prompt could be designed to dynamically adjust based on the study type (e.g., experimental vs. observational vs. review).  
	- This would ensure that even non-experimental studies contribute relevant insights (e.g., discussion on sex/gender disparities in systematic reviews).  

	##### 2) Named Entity Recognition (NER) Using a BERT Model  
	- A fine-tuned NER model (such as a BERT model fine-tuned for medical texts) could be employed to automatically detect key terms (e.g., "age," "ethnicity," "sex," "socioeconomic status") from text.  
	- This would allow for a structured extraction of intersectional factors without requiring explicit prompting for each one.  

	##### 3) Hybrid Approach (LLM + Traditional NLP)  
	- The LLM could first categorize the study (e.g., clinical trial vs. observational vs. review).  
	- Then, an NLP pipeline could extract structured numerical and categorical data (e.g., participant demographics, biometric data, geographic origin).    

#### 3. Sharing your results
- You can use any mean to share the result, jupyter notebook, python script, etc.

#### 4. Use of AI to do the test
- You are free to use any tools you want to do that test. However do not overcomplicate it and be sure your code run. We prefer something simple but that works, than an overcomplicated solution we cannot read or run.

## Seting up your environment
You can use these options as you prefer

### Google Collab

Here is a link to a [google collab notebook](https://colab.research.google.com/drive/18sxFHCgMxXxr6KmQSZ7lVSIMd4lkJUhY?usp=sharing) for you to start. You do not have to use it, but it's there to make the task easier for you. 
When you finish, push the notebook copy here.

### Conda / Virtualenv 

We recommend the use of [Bioconda](http://bioconda.github.io/) or [Virtualenv](https://virtualenv.pypa.io/en/latest/installation.html) to facilitate cleaning and reproducibility of the exercise. Make sure that you have installed and configured the necessary packages for the installation.   

Once you are done, export your file with your environment. 

**conda**
```
mkdir envs
conda env export > enviroment.yaml
```

**virtualenv**

```
mkdir envs
pip freeze > requirements.txt
```

### Git repository

#### 1. Forking this repository

You need to copy this repository to start to work in your own GitHub. 

Click the **fork button** on the top right of the repository webpage on GitHub. GitHub will create a copy of the repository under your account. 

#### 2. Cloning your fork

Once you fork the project, you will have a copy of the repository:
```
https://github.com/<your_username>/recruitment_test 
```
**Clone** this repository in your local machine. 





