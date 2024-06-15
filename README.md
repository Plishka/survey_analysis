# Stack Overflow Annual Developer Survey 2023 Results Analysis

## **Project Overview**
Using the Stack Overflow Annual Developer Survey 2023 data and a Python Notebook, this project aims to answer the following questions:
1. How many respondents completed the survey?
2. How many respondents answered all the mandatory questions?
3. What are the median values for the respondents’ work experience (WorkExp)?
4. How many respondents work remotely?
5. What percentage of respondents program in Python?
6. How many respondents learned to program through online courses?
7. What is the average and median compensation among respondents who program in Python in each country?
8. What education levels do the top 5 highest-paid respondents have?
9. What percentage of respondents program in Python in each age category?
10. Which industries are the most prevalent among respondents (who work remotely) in the 75th percentile for average compensation?

## **Steps and Code**

### **1. Number of Respondents Completed the Survey**
```python
import numpy as np
import pandas as pd

survey = pd.read_csv('C:/Users/plish/Desktop/Python_HW/Stack Overflow Developer Survey 2023/survey_results_public.csv')
schema = pd.read_csv('C:/Users/plish/Desktop/Python_HW/Stack Overflow Developer Survey 2023/schema.csv')

# Number of respondents completed the survey
Q1 = survey['ResponseId'].nunique()
print(f'{Q1} respondents took part in the survey')
# 89,184 respondents took part in the survey

### **2. Number of Respondents Who Answered All Mandatory Questions**
```python
# Number of respondents who answered all the mandatory questions
questions = set(schema.qname.unique()) & set(survey.columns)  # Connecting survey with survey schema to get all mandatory questions
Q2 = survey.dropna(subset=questions).shape[0]
print(f'{Q2} respondents have answered all the questions in the survey')
# 2,032 respondents have answered all the questions in the survey

