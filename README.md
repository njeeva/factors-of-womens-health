# What are the factors that can help us predict how well each US state is doing in terms of women's health?

Using data from the [CDC](https://www.cdc.gov/nchs/maternal-mortality/MMR-2018-State-Data-508.pdf) and the [The Henry J. Kaiser Family Foundation](https://www.kff.org/state-category/womens-health/), an analysis of various factors including percentage of women aged 19-65 who are uninsured, percentage of women without a primary care physician, racial demographics, number of heart disease deaths, and maternal mortality rates from each state was conducted. The impact of each of these factors on the percentage of women who report poor of fair health in each state was determined. The effect of two of the variable evaluated, the nuber of heart disease death and maternal mortality rates, on this percentage is seen below. These variables were chosen since heart disease is the leading cause of death of women in the United States, and maternal mortality rates have been climbing at an alarming pace these last few decades.

![Heart disease](https://github.com/njeeva/factors-of-womens-health/blob/master/Heart%20Disease%20and%20Health%20Status.JPG)

![Maternal Mortality](https://github.com/njeeva/factors-of-womens-health/blob/master/Maternal%20Mortality%20and%20Health%20Status%20by%20State.JPG)

A number of regression models were run, with the final yielding an R square value of 0.707 and a standard error of 0.017. The F significance value was 2.14 x 10^-5. A table with each variable's coefficient, standard error and p-value can be seen below.

![Results](https://github.com/njeeva/factors-of-womens-health/blob/master/Results.JPG)


### Step by Step Analysis
1. First, the following data sets were downloaded:
    * [Women Who Report Fair or Poor Health Status by Race/Ethnicity](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Fair%20or%20Poor%20Health%20Status%20by%20RaceEthnicity.csv)
    * [Women Who Report Not Seeing a Doctor in the Past 12 Months Due to Cost](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Not%20Seeing%20a%20Doctor%20in%20the%20Past%2012%20Months%20Due%20to%20Cost.xlsx)
    * [Women Who Report Having No Personal Doctor or Health Care Provider](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Having%20No%20Personal%20Doctor%20or%20Health%20Care%20Provider.csv)
    * [Popultion Distribution by Race](https://github.com/njeeva/factors-of-womens-health/blob/master/Population%20Distribution%20by%20Race.xlsx)
    * [Number of Heart Disease Deaths per 100,000 Population by Gender](https://github.com/njeeva/factors-of-womens-health/blob/master/Number%20of%20Heart%20Disease%20Deaths%20per%20100%2C000%20Population%20by%20Gender.csv)
    * [Health Insurance Coverage of Women 19_64](https://github.com/njeeva/factors-of-womens-health/blob/master/Health%20Insurance%20Coverage%20of%20Women%2019_64.xlsx)
  
 2. Then, in the first spreadsheet, with each state in the first column and corresponding Health Status in the second, append the additional data from the new spreadsheets with the VLOOKUP tool.
 
 3. Run a linear regression model with Excel using the data analysis toolkit.
 
 4. Depending on the summary output, adjust the variables included in the analysis in order to optimize and find the best fit.
