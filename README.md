# Recruitment Test: Extraction of scientific data and detection of bias in research articles

## Task description

We propose a possible scenario in which we want to evaluate the information in a multitude of scientific articles to find biases. The objective of this task is to find relevant information for further analysis by automatically identifying the information present and missing in the text of an example article.  

#### 1. Extract relevant information

- Studied disease condition
- Number of patients 
- Number of patients in case and control groups
- Give me the sex of the patients (if applicable) 
- Give me the origin of the patients (if applicable)

Use an LLM model to identify this information and include comments explaining the prompt engineering and reasoning used. 

#### 2. Think about the text

- Do you find that there is relevant information missing from the data we have asked for?
- Can they be inferred? How?

## Seting up your environment

### Conda / Virtualenv 

We recommend the use of [Bioconda](http://bioconda.github.io/) or [Virtualenv](https://virtualenv.pypa.io/en/latest/installation.html) to facilitate cleaning and reproducibility of the exercise. Make sure that you have installed and configured the necessary packages for the installation.   

Onece you are done, export your a file with your environment. 

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

#### 3. Commit your results in a new branch

Once the exercise is finished create a new branch: **recruitment_test_results** and save the final changes made to the repository. 

We recommend the use of several **commits**, but it is not relevant for this exercise.

#### 4. Explaining your results in a pull request.

Opens a pull request to the original repository explaining the results of the exercise. 




