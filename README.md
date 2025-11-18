Case-Study-Analyzing-Job-Market-Data-in-Power-BI

You can read the full article on this project here.
In this Power BI case study, we’ll explore a real-world job posting dataset to uncover insights for a fictional recruitment company called DataSearch. We’ll use Power Query to investigate and clean the data to find out what skills are most in-demand for data scientists, data analysts, and data engineers. We’ll then use DAX to build insightful visualizations of our findings. Finally, We’ll bring it all together using everything Power BI has to offer to create a business dashboard so that we can answer questions for the DataSearch team.

Project Objectives
Investigate market trends for data science roles

The context An employee recruiting firm DataSearch,needs to uncover job trends
Thetask Discover trends in jobs and skills within the data science industry
The dataset Factitious collection of key details from job postings. The Dataset contains data about 25,114 job postings and 17 columns information about each job posting (Title, Date, Industry, Skills, ... )

Data analysis Pipeline:
Checking Data
Exploring Data
Analyse and Visualise Data
Dashboarding
Communicating Insights

Step 1: Exploratory Analysis
We'll start this Power BI case study by importing and cleaning the job posting dataset using Power Query. Once we’ve done this, it’s time to do some initial data exploration.

First, I imported and loaded the dataset into Power BI. Then, using Power Query tool, 93% of values for Max and Min pay column were null values. This indicates that more than 90% of companies do not mention Maximum and Minimum of salary in their job postings. After than by sorting the Number of applicant column in a decending order, I understood that the most popular industries were Marketting and Adevrtisement, Computer Software, and Broadcast Media, respectively.

More Experienced, Higher Level
Next, I want to obtain an idea of the relation between the Years of Experience and the Job Position level (e.g. Entry Level). To do so, I visualised the average Years of Experience and column and the Job Position Level column using a Treemap and a Bar chart.

<img width="2032" height="1795" alt="image" src="https://github.com/user-attachments/assets/9e33a153-66e5-4a3f-ad8f-08fb6c4845c1" />


<img width="1070" height="590" alt="image" src="https://github.com/user-attachments/assets/b14cbd5c-fee0-42b8-875d-3fc2737225b7" />


It is observed that the average experience years required for a Executive level job is around 15 years and you can land an Internship with less than a year experience. At 15.17 years, Executive had the highest Average of Years of Experience and was 4,047.13% higher than Internship, which had the lowest Average of Years of Experience at 0.37 year. Moreover, across all 6 Job Position Levels, Average of Years of Experience ranged from 0.37 to 15.17 years.

Job Posting Trend Analysis
Next, we are interested in observing the trend of job postings in time. So we visualise the Count of Job Posting IDs over Job Posting Date as time axis.

<img width="1775" height="1190" alt="image" src="https://github.com/user-attachments/assets/859f8071-b18e-4445-9b11-72f2fa76dde7" />


It is evident that the first quarter of 2020 the number of job positions has been the lowest due to the rise of Covid-19. Between January 2017 and December 2021, Mid-Senior level had the largest increase in Count of Job Postings (174.48%) while Internship had the largest decrease (33.33%). The most recent Count of Job Postings anomaly was in September 2021, when Director had a low of 1. Count of Job Postings for Internship started trending up on February 2021, rising by 300.00% (3) in 4 months.

Filtering for Data Related Job Titles
Now it's time to dig deeper into the dataset to gain info about data related jobs: Data Scientist, Data Analyst, Data Engineer, Machine Learning Engineer, and Data Science Manager. We start by analysing the number of job postings for each job title.

<img width="2187" height="1215" alt="image" src="https://github.com/user-attachments/assets/d59f1fe6-ee8e-463b-b040-f9739514143a" />


At 3,462, Data Engineer had the highest Count of Job Postings and was 14,952.17% higher than Data Science Manager, which had the lowest Count of Job Postings at 23. Data Engineer accounted for 47.74% of Count of Job Postings. Across all 5 Job Titles, Count of Job Postings ranged from 23 to 3,462.

Effect of Years Experience on Salary
In the next step of our EDA, we are interested in identifying influential factors on job market trend. One of the integral parts of a job is the compensation. Here, we analyse the effect of years of experience on each jab's offered salary.

<img width="2320" height="1252" alt="image" src="https://github.com/user-attachments/assets/a5b064c3-133f-43bd-81f4-49b0d40e6fbd" />


It is obvious that the more the years of experience, the highere salary. Also, we observe that the Data Analysts earn the least compared to other data related jobs. A bit dissapointing! However, we must keep in mind that more than 93% of values for Max and Min pay columns (which we used to calculate the Average pay for each job title) were null values, so we connat draw any major concolusions.

Step 2: Analyzing Market Trends
In our second analysis step we continue to apply our Power BI skills to extract data insights with tools like DAX and begin to build unique data visualizations.

Key Insights we have Identified So Far:

Job postings are gradually increasing in number.
Data Engineers, Data Scientists, and Analysts are indemand!
Tech industries need data science roles the most.
Salaries are trending upward as expected.
In our second step, we are going to analyse our data to provide insights on the following:

Correlation between skills and job title
Top industries and companies
Potential recommendations
We want to follow a goal-oriented approach in our analysis, so, we must keep our final purpose in mind and identify the following as we go forward in our data analysis project:

Key findings to focus
Visualizations to share
Communication style
Skill analysis
Using only the two columns Job Posting ID and Job Skills, we creat a second Table called Job Skills. In the new table we remove the extra characters in the column Job Skills such as brackets [], quotes ", and extra spaces. I have also used the Trim and Clean features to remove the extra spaces in each cell. Then, we split this column into rows to seperate the list of skills for each job on a seperate row.



Next, I visualised the count of Job Skills to gain an innitial idea of the most required skills.

<img width="2030" height="1132" alt="image" src="https://github.com/user-attachments/assets/1202f537-34e6-4090-ae2d-78342539af8c" />


We observe that the count of Job Skills was highest for python at 3,931, followed by sql and cloud. Python accounted for 7.44% of Count of Job Skills. Across all 165 Job Skills, Count of Job Skills ranged from 1 to 3,931.

Skill Likelihood in Job Posting
Here, I used DAX to identify the probability of a certain skill occurance in a job posting. To do so, we use the basic probability principles. The probability of a certain skill existing in a job ad, can be calculated at the count of all the job postings that contain this skill over the total number of all job postings. Therefor, I created three measures called Skill Count , Posting Count, and % of Skill in Posting that calculated the required chance. Then I created a Matrix to visualise the result. I also added a slicer, so that it would be easier to filter for a specific skill.

<img width="2052" height="1172" alt="image" src="https://github.com/user-attachments/assets/8ebe6655-bedf-4e5c-8137-f718cd00e8ac" />


Trends in skills over time
Next, let's analyse the trend of skills in job postings over time. This can give us a good idea of what skills are more in demand in certion time periods. We want a a time-series graph, so we use a Line Chart to visualise the % Skill in Postin over time by using Posting Date and use Job Titles from our Job Skills table as a legend. The result is the following graph:

<img width="1855" height="1000" alt="image" src="https://github.com/user-attachments/assets/5caa9d3d-d690-4e2c-be26-142f30ed4cc0" />


We can observe that although the metrics have fluctuations on a short-term basis, the top 10 skills maintain at consisted deman over the past few years. Moreover, across Job Skills, spark had the most interesting recent trend and started trending down on 2017, falling by 6.61% (1.29%) in 4 years.

Deep dive into key job descriptions
Next, we are interested in exploring the companies and industries that are looking for data-related roles. To do this, I visualised the Average years of experience and posting count by job position level and company industry in a scatter plot, along with a table containing posting count, job title and company name. This way, I can find out which industry and company is mostly looking for which job position level and with how many years of experience.

<img width="2065" height="1740" alt="image" src="https://github.com/user-attachments/assets/3110acd8-2b30-4946-9137-f84ccb70ef38" />


It is evident that there is a large demand for Mid-senior scientists with an average of 5.37 years of experience in the internet industry.

<img width="1500" height="1660" alt="image" src="https://github.com/user-attachments/assets/5e2fa61b-ea66-4042-a2a1-09dc2370cd3f" />


Using the table, we observe that the company Toptal is hiring a large number of Data Engineers (994) and Data Scientist (673). Staffing & Recruiting had the highest Average of Years of Experience (4.96) and Internet had the highest Posting Count (5052).

Step 3: Building Dashboard
Now it’s time to hand over the final deliverable. We’ll combine all of the job listing insights we’ve discovered into an interactive Power BI dashboard for the DataSearch team.

Begin dashboard templates
We decide to summerise our findings in three pages Jobs, Skills, Company, introduced in the Home page. We used template pictures for the background to make our final dashboard more organised.

Designing a dashboard layout
<img width="3092" height="1730" alt="image" src="https://github.com/user-attachments/assets/4c79ca8d-1671-4cf4-bdda-6534710754a0" />


Exploring top skills for jobs
<img width="3092" height="1740" alt="image" src="https://github.com/user-attachments/assets/a23c2919-c543-4714-ac96-06df2f9b5536" />


Salary gauge for companies
<img width="3095" height="1730" alt="image" src="https://github.com/user-attachments/assets/dc5748e6-e8a3-40f4-bf5a-4df0ab351fb8" />


Adding interactivity with bookmarks
With the help of icons and bookmarking them, I was able to make my dashboard even more interactive. This id the final results where the icons are clickable and make working with the dashboard a lot easier for the end-user. This is the final result:

Home Page: <img width="3070" height="1727" alt="image" src="https://github.com/user-attachments/assets/b039eb25-5d16-4e3c-a45e-74ce6f72680a" />


Jobs Page: <img width="3090" height="1722" alt="image" src="https://github.com/user-attachments/assets/738fc2aa-1dcb-4849-ab78-dfc54b600f15" />


Skills Page: <img width="3095" height="1735" alt="image" src="https://github.com/user-attachments/assets/03dd7396-53dd-42b8-9c21-363f6f382429" />


Company Page: <img width="3090" height="1722" alt="image" src="https://github.com/user-attachments/assets/7cea831d-980f-4089-866b-9de15d00e8de" />


About
In this Power BI case study, we’ll explore a real-world job posting dataset to uncover insights for a fictional recruitment company called DataSearch.

Resources
 Readme
 Activity
Stars
 0 stars
Watchers
 1 watching
Forks
 0 forks
Report repository
Releases
No releases published
Packages
No packages published
Footer
