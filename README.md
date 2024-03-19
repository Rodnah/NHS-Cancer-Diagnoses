# NHS - Cancer Incidence in 2 Years


## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Scraping](#data-scraping)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Results](#results)
- [Recommendations](#recommendations)
- [References](#references)
 

### Project Overview
This project analyzes cancer diagnoses trends using NHS England data. It looks at differences between genders and changes over two specific years. Key areas include prostate, bowel, lung, and breast cancer. The aim is to find insights for better prevention, screening, and treatment strategies.

![Untitled](https://github.com/Rodnah/NHSCancerStats/assets/147203468/c06413b5-f18d-42cc-b201-0625fff06ecb)




### Data Sources
The primary dataset was scrapped from [NHS England](https://digital.nhs.uk/data-and-information/publications/statistical/cancer-registration-statistics/england-2021---summary-counts-only/cancer-incidence) and exported to a CSV file. This CSV contains detailed information about various parameters within the dataset.

### Tools
1. BeautifulSoup - Data Scraping
2. Excel - Data Cleaning and Preprocessing
3. Python - Data Analysis
4. Matplotlib  - Data [Visualization](http://localhost:8888/notebooks/NHS%20-%20Cancer%20Incidence%20in%202-Years.ipynb)
   
### Data Scraping
I performed the following tasks:
1. Selected BeautifulSoup as my scraping tool
2. Inspected the website
3. Extracted and exported the data
   
Excerpt of some code worked with:

```python
# Iterate through each table
for table in tables:
    # Extract the data from each row
    rows = table.find_all("tr")
    for row in rows:
        # Extract the data from each cell in the row
        cells = row.find_all(["th", "td"])
        row_data = [cell.get_text(strip=True) for cell in cells]
        data.append(row_data)
```

### Data Cleaning
In the initial data preparation phase, I performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis
EDA involved exploring the data to answer critical questions, such as:
1. What's the difference between registered diagnoses for both years and in both genders?
2. What's the difference between the diagnoses registered for similar cancer sites for both genders in 2019?
3. What's the difference between the diagnoses registered for similar cancer sites for both genders in 2021?
4. What is the proportionate change in diagnosis registered for both genders and their similar cancer sites.


### Results
The analysis results are summarized as follows:
1. The registered diagnoses between both years:
a. For males, notable differences include:
i. Prostate cancer had more incidence in 2019.
ii. Bowel cancer had more incidence in 2021.

b. For females:
i. Bowel and breast cancer had more registered diagnoses in 2021.
ii. Differences for other cancer sites were negligible.

2. A comparative analysis reveals that males had a total number of registered cancer diagnoses in both years.

3. Lung cancer exhibited the most significant proportionate change between both years and for both genders, while leukaemia had the least proportionate change.


### Recommendations
Based on the analysis, I recommend the following actions:

1. Allocate resources to tackle the increase in bowel cancer diagnoses for both genders in 2021, focusing on prevention and treatment.
2. Give priority to lung cancer screenings, considering the significant changes across genders and years.
3. Review breast cancer screening programs to ensure they're practical, especially with more cases in 2021, and keep an eye on cancer trends for timely policy adjustments.




### References
- [NHS England](https://digital.nhs.uk/data-and-information/publications/statistical/cancer-registration-statistics/england-2021---summary-counts-only/cancer-incidence)
- [Python Web Scraping Series](https://www.youtube.com/playlist?list=PLUaB-1hjhk8G-xVXA5FxT2cLNzd87GInr)
