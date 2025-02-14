# Determinants-of-College-GPA
This is the first of a series of three projects completed for my Applied Econometrics course of UCLA's Master of Quantitative Economics. The objective is to identify the best predictor of students' GPA in college. To achieve this, we test multiple SLR models with the appropriate variable transformations and robustness checks. We conclude that, in our dataset, students' high school percentile is the best predictor of their college GPA.
## Project Motivation
GPA is a key indicator of a student's academic ability and mastery of material throughout college. Many schools require students to maintain a minimum GPA to graduate, and achieving a high GPA often qualifies students for academic honors and scholarships. Beyond the academic environment, GPA can play a significant role in career opportunities, as employers and internship programs sometimes use it as an initial screening criterion in their hiring processes.

In this project, we aim to analyze the factors that influence GPA using the gpa2 dataset from the Wooldridge package. Our motivation is to understand how past academic performance, such as high school grades, and demographic factors, such as gender and ethnicity, affect college GPA.

## Data Description
The data used for our project is the gpa2 dataset from the Wooldridge package (Wooldridge, 2013). This dataset comes from a midsize research university supporting men’s and women’s athletics at the Division I level. The sample consists of 4,137 students who attended the university, including both athletes and non-athletes.

The academic year during which the data was collected was anonymized for confidentiality reasons. Our findings and conclusions drawn from this dataset may not be generalizable to other educational institutions since the source of our data comes from a single midsize research university.

The dataset contains 12 variables, each capturing the students' key academic and demographic characteristics. The variables are as follows:

1. sat: The student’s total SAT score, combining both verbal and math components.

2. tothrs: The cumulative study hours (i.e., credit hours) up to the fall semester. This interpretation is based on examining the distribution of this variable in a histogram (refer to ‘Description of Data Analysis’ section).

3. colgpa: The student’s GPA after the fall semester.

4. athlete: An indicator variable equal to 1 if the student is an athlete.

5. verbmath: The student’s ratio of SAT scores; verbal score / math score.

6. hsize: The size of the student’s graduating high school class, measured in 100s.

7. hsrank: The student’s rank in their high school graduating class.

8. hsperc: The student’s high school percentile, measured from the top (e.g., top 20%).

9. female: An indicator variable equal to 1 if the student is female.

10. white: An indicator variable equal to 1 if the student is white.

11. black: An indicator variable equal to 1 if the student is black.

12. hsizesq: The size of the student’s graduating high school class, measured in 100s, squared.

Based on the above variable descriptions, we chose the GPA after the fall semester (colgpa) as the dependent variable and sat, tothrs, hsperc, female, and white as the independent variables. These choices were made based on their potential influence on a student's academic performance:

1. SAT score (sat): SAT scores are commonly used in college applications to assess academic ability, verbal reasoning, and mathematics. We hypothesized that higher SAT scores positively correlate with college GPA, as students with stronger academic preparation may perform better.

2. Cumulative study hours (tothrs): The total number of credit hours reflects the student's academic level, engagement, and experience. While we cannot fully conclude that GPA improves over time in college, we hypothesized a slightly positive correlation between cumulative hours and GPA, as students may develop better time management skills and study habits as they progress through college.

3. High school percentile (hsperc): This variable measures students' past academic performance relative to their high school class rank. We hypothesized that students who graduated at the top of their class (i.e., with a smaller hsperc value) would receive a higher GPA, implying a negative correlation between high school percentile and college GPA.

4. Gender (female) and Race (white): These indicator variables were included to explore potential differences in academic performance between male and female students and students of different racial backgrounds. We were unsure about the effect of the female variable. However, we hypothesized a positive correlation between the white variable and college GPA, as socioeconomic and institutional factors may influence academic outcomes and access to educational resources.

## Results

After testing our 4 models (hsperc, sat, square root of hsperc (hsperc_sqrt), and logarithm of hsperc (log_hsperc)), we concluded that the square root of high school percentile (from the top - 1% being the best) was the best predictor for college GPA.
However, this result may lack robustness due to our approach's limitations. 
By relying solely on univariate models, we omitted potentially significant interactions and contributions from SAT, the other predictor suggested by Boruta and Mallows CP.
Furthermore, when interpreting our model parameters, it’s essential to distinguish statistical significance from economic significance. 
The square root transformation of hsperc (hsperc_sqrt) achieves statistical relevance due to better-fitting residuals and variance reduction. 
However, the economic significance - what it tells us about the practical or causal relationship between high school performance and college GPA - remains ambiguous. 
A multivariate approach could capture a more comprehensive picture of factors influencing GPA, potentially revealing that a combination of SAT scores, family background, and high school performance jointly offer a more economically interpretable model.
