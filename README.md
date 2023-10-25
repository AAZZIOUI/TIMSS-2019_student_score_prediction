# TIMSS STUDENTS MATH SCORE PREDICTION MODEL
***
## Table Of Content:
1. [Project status](#project-status)
2. [Project overview](#project-overview)
3. [About Data](#about-data)
4. [Steps to tackle the project](#steps-to-tackle-the-project)

## Project Status
***
- [x] Validation of the country score calculation process 
- [ ] Data wrangling

## Project Overview
***

>TIMSS, which stands for Trends in International Mathematics and Science Study, is a global evaluation program that tracks changes in student performance in mathematics and science. This assessment occurs on a quadrennial basis, with the most recent round taking place in 2019. Notably, Moroccan students have historically achieved relatively low scores in these assessments. Nevertheless, the Ministry of Education has been implementing novel educational methodologies in recent years. My aim is to assist in assessing the potential impact of these new approaches on Moroccan students' TIMSS scores before the next assessment cycle.

>This initiative involves the development of a machine learning model designed to predict the TIMSS mathematics scores of Moroccan students based on specific information related to these students. The primary objective is to utilize this model to estimate a student's score, taking into consideration their social, economic, and environmental context. Subsequently, the ministry can compare these estimated scores with the actual scores obtained by students who have learned mathematics through the new teaching approaches and undergone a similar evaluation to that of the TIMSS assessment.

## About Data:
***
>Data source : https://timss2019.org/international-database/ 

I downloaded: 
* SPSS data related to Morocco for both 4th and 8th grades.
* TIMSS official user guide: https://timss2019.org/international-database/downloads/TIMSS-2019-User-Guide-for-the-International-Database-2nd-Ed.pdf 
* Codebooks in order to understand data content:
    * https://timss2019.org/international-database/downloads/T19_G4_Codebooks.zip
    * https://timss2019.org/international-database/downloads/T19_G8_Codebooks.zip


## Steps to tackle the project:
***
### 1. Understand how TIMSS score is actually calculated.
After many trials, we found out that the Moroccan Score is calculated as follows:

$$ SCORE_{4^{th}G} = \frac {\Sigma_{i=1}^{n=7723} (PV_{i} \times WEIGHT_{i})}{\Sigma_{i=1}^{n=7723}  WEIGHT_{i}}$$  

and 

$$ SCORE_{8^{th}G} = \frac {\Sigma_{i=1}^{n=8458} (PV_{i} \times WEIGHT_{i})}{\Sigma_{i=1}^{n=8458}  WEIGHT_{i}}$$ 

With:
* PV: the mean of all Plausible math values of a student. it is directly calculated from data.
* WEIGHT: Total student weight given in the data. TIMSS applies complex weighting and calibration procedures to ensure that the sample of students is representative of the entire population. These procedures are used to adjust for variations in the sampling process. The official country score takes these procedures into account.
* 7723 being the number of Moroccan students participating in the study from 4th grade.
* 8458 being the number of Moroccan students participating in the study from 8th grade.

> __Note__

>Even if it may not be exactly the same as the official country score reported by TIMSS, the *mean of plausible scores* for all students within a country is a reasonable estimate of the country's overall performance. (see timss-2019_score_calculation.ipynb for more information)

