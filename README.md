# data_analyst_jobs_search

## Abstract

Data analysis is a process of inspecting, cleansing, transforming and modeling data with the goal of discovering useful information, studying trends and supporting decision-making. Data analysis has multiple facets and approaches, encompassing diverse techniques under a variety of names, and is used in different business, science, and social science domains. In today's business world, data analysis plays a role in making decisions more scientific and helping businesses operate more effectively and efficiently.

![images](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/services.jpg)

## Motivations for this project

Amidst the COVID19 pandemic many people lost their jobs, with this dataset it is possible to hone the job search so that more people in need can find employment in technical positions such as data/business analyst.
This dataset was created by picklesueat and contains more than 2000 job listings for data analyst positions, with features such as:


- Salary Estimate
- Location
- Company Rating
- Job Description
- Industry
- and more

### Questions for exploration:
- Top industries and sectors currently hiring
- Find the best jobs by salary and company rating
- Explore skills required in job descriptions
- Predict salary based on industry, location, company revenue

## Methods

### Libraries Used
- Pandas: data manipulation and analysis tool built on Python
- Numpy:  library for the Python programming language, adding support for large, multi-dimensional arrays and matrices
- Matplotlib: comprehensive library for creating static, animated, and interactive visualizations in Python
- Seaborn: Python data visualization library based on matplotlib
- Folium: a powerful Python library that helps you create several types of Leaflet maps
- Plotly: interactive, open-source, and browser-based graphing library for Python
- Opencage.geocoder:  an API that can be use to look up coordinates of places, and also find out the place a set of coordinates corresponds to
- Wordcloud: a visual representation of text data
- Yellowbrick: a suite of visual analysis and diagnostic tools designed to facilitate machine learning with scikit-learn.
- Scikit-Learn: predictive data analysis

### Data Cleaning

1. Remove 'Unnamed: 0' column --> .drop() method
2. Parse the Lower and Upper Bounds of Salary Estimate, Company Size, and Revenue for granular analysis --> for loop with .replace(), .split() and .strip() methods
3. Remove the "/n" in the Company Name column --> for loop with .split() method
4. Rows with -1, '-1.0', and '1' were in place in certain columns. It seems like these values were input in place as Null values. I replaced them relevant values in each respective column.

## Data Analysis

#### What are the top 20 industries hiring during COVID19?

![top20industries](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top20industry.jpg)

- The top 2 industries (IT Services and Staffing & Outsourcing) make up 29% of all Data Analyst jobs with a non-null Industry label. My guess would be that a lot of hiring is done by an intermediary Staffing & Outsourcing company as opposed to the actual job Industry.

- Outsourcing is cost- and time-efficient since it keeps finances flexible, not fixed. In-house – Hiring new staff members don't come cheap. Companies would have to face financial challenges with fixed HR expenses and even intangible costs like time to hire a full-time team. Companies are cutting costs due to the COVID19.

#### What are the top 20 companies hiring during COVID19?

![top20companies](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top20companies.png)

- As previously mentioned, the first 8 companies are employment and recruitment agencies. The only non-staffing companies are Apple, MUFG (Financial Services), Citi, Bank of New York Mellon, and Molina Healthcare. Apple is a major technology company that designs, develops, and sells consumer electronics, computer software, and online services. Financial institutions and healthcare are essential businesses, required to combat the unprecedented times of COVID19.


#### What is the distribution of a data analyst's salary?

![histograms](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/salarydistribution.png)

- The lower and upper bound salary estimates are skewed right, meaning the mean is greater than the median.

#### What are the top industries hiring ordered by median salary?

![top20industrymediansalary](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top20mediansalarynonadjust.png)

- The box plots seem to be all over the place. News outlet, chemical manufacturing, hotels only have one point so it's not truly representative since it's one sample for each of those industries. Let's establish a baseline of minimum number of job listings per industry. We will set the cutoff at 15 since that accounts for 90% of non-null postings.

#### Lower Bound of Median Salary by Industries with at least 15 job postings

![top10induslowersalary](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top10indlowsalary.png)

#### Upper Bound of Median Salary by Industries with at least 15 job postings
![top10indusuppersalary](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top10induppersalary.png)


#### Top 15 industries by max revenue

![top10sectorsmarev](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/top10industryrevenue.png)

- The top 15 industries can be deemed "essential businesses":
- Drug stores, grocery stores and supermarkets need to be open for sanitation supplies, food, and essential goods.
- Utilities, cable/TV/internet providers are the main sources for productivity since many companies are directing employees to work from home. Students of all ages are   engaged in distance learning. Since shelter in place protocol, people turn to the internet and TV for entertainment.
- Public transportation is vastly utilized by millions of people in the United States especially in densely populated cities such as New York City, San Francisco, and Los Angeles.


### Which states offer the most data analyst roles?

![choroplethmap](https://github.com/aclao89/data_anaylst_jobs_search/blob/master/images/choropleth.html)
- While Silicon Valley is the nation's leading technology-driven economy, there are many notable tech hubs in the US with exciting opportunities. https://builtin.com/tech-hubs 

1. It's no surprise that California has the most job offerings due to its population, size, and location of Silicon Valley.
2. Austin, Texas is one of the upcoming tech hubs forming outside of Silicon Valley. The cost of living is much lower than Silicon Valley which attracts many college graduates and young professionals.
3. New York City is a global icon on the forefront of culture, finance, and media. Digital media platform, finance tech, and real estate are some of the few popular industries that employ data analyst roles.
4. Chicago, Illinois has roughly 6,000 tech companies with popular industries of fintech, healthtech, and big data.  
