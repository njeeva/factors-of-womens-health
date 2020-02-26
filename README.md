# What are the factors that can help us predict how well each US state is doing in terms of women's health?

Using data from the [CDC](https://www.cdc.gov/nchs/maternal-mortality/MMR-2018-State-Data-508.pdf) and the [The Henry J. Kaiser Family Foundation](https://www.kff.org/state-category/womens-health/), an analysis of various factors including percentage of women aged 19-65 who are uninsured, percentage of women without a primary care physician, racial demographics, number of heart disease deaths, and maternal mortality rates from each state was conducted. 

The impact of each of these factors on the percentage of women who report poor or fair health in each state was determined. The effect of two of the variable evaluated, the nuber of heart disease death and maternal mortality rates, on this percentage is seen below. These variables were chosen since heart disease is the leading cause of death of women in the United States, and maternal mortality rates have been climbing at an alarming pace these last few decades.

![Heart disease](https://github.com/njeeva/factors-of-womens-health/blob/master/Heart%20Disease%20and%20Health%20Status.JPG)

![Maternal Mortality](https://github.com/njeeva/factors-of-womens-health/blob/master/Maternal%20Mortality%20and%20Health%20Status%20by%20State.JPG)

A number of regression models were run, with the final yielding an R square value of 0.707, a multiple R value of 0.841, an adjusted R square value of 0.651 and a standard error of 0.017. The F significance value was 2.14 x 10^-5. A table with each variable's coefficient, standard error and p-value can be seen below.

![Results](https://github.com/njeeva/factors-of-womens-health/blob/master/Results.JPG)

### Data Interpretation
This data shows that while the percentage of women in each state reporting poor or fair health status cannot be fully calculated using the variables listed above, they still have a clear impact on the health of women. The R square value demonstrates that over 70% of the data points can be explained by the percentage of state that is nonwhite, the percentage of women 19-65 in the state who are uninsured, the maternal mortality rate and the number of heart disease deaths in the state. It is important to note that while the p-values of most of these variables is less than 0.05, the maternal mortality rate is slighlty higher at 0.0697, and the percentage nonwhite is much higher at 0.257. As a result, these factors play a slighlty less significant role on the final health status results. The nonwhite variable coefficient is unexpected, showing that increasing the percentage of nonwhite population in a state actually improves the overall women's health status in a given state. After further analysis, it seems that this is due to the fact that Asian women report much lower rates of poor health status than white, hispanic or black women.

As a whole, in order to address women's health issues throughout the United States, it is important that governments, non profit organizations and communities address these factors. A 1% decrease in the percentage of uninsured women in a state, will improve the rates of women reporting poor or fair health status by 0.22%. Improving healthcare coverage among uninsured women can have a significant effect on the health status of women throughout the state.

### Step by Step Analysis
1. First, the following data sets were downloaded:
    * [Women Who Report Fair or Poor Health Status by Race/Ethnicity](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Fair%20or%20Poor%20Health%20Status%20by%20RaceEthnicity.csv)
    * [Women Who Report Not Seeing a Doctor in the Past 12 Months Due to Cost](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Not%20Seeing%20a%20Doctor%20in%20the%20Past%2012%20Months%20Due%20to%20Cost.xlsx)
    * [Women Who Report Having No Personal Doctor or Health Care Provider](https://github.com/njeeva/factors-of-womens-health/blob/master/Women%20Who%20Report%20Having%20No%20Personal%20Doctor%20or%20Health%20Care%20Provider.csv)
    * [Popultion Distribution by Race](https://github.com/njeeva/factors-of-womens-health/blob/master/Population%20Distribution%20by%20Race.xlsx)
    * [Number of Heart Disease Deaths per 100,000 Population by Gender](https://github.com/njeeva/factors-of-womens-health/blob/master/Number%20of%20Heart%20Disease%20Deaths%20per%20100%2C000%20Population%20by%20Gender.csv)
    * [Health Insurance Coverage of Women 19_64](https://github.com/njeeva/factors-of-womens-health/blob/master/Health%20Insurance%20Coverage%20of%20Women%2019_64.xlsx)
  
 2. Then, in the first spreadsheet, with each state in the first column and corresponding Health Status in the second, append the additional data from the new spreadsheets with the VLOOKUP tool.
 
 3. Using the [CDC maternal mortality rates per state](https://www.cdc.gov/nchs/maternal-mortality/MMR-2018-State-Data-508.pdf), fill in an additional column on the spreadsheet. This data set does not have information for every state. Remove all the states without maternal mortality data.
 
 4. Run a linear regression model with Excel using the data analysis toolkit on all the data points with a complete data.
 
 5. Depending on the summary output, adjust the variables included in the analysis in order to optimize and find the best fit.
