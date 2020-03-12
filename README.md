# Chicago Insurance Redlining (Regression Analysis) 

![Kept Out](images\redlining-lead.jpg)

## Are people of color more likely to be turned down for a mortgage in Chicago than their white counterparts, even when they make the same amount of money?

## Introduction #
The term redlining originates from the 1930s practice of color-coding maps of cities based on different neighborhoods’ eligibility to receive a loan or mortgage. The lowest ranked neighborhoods were often literally lined in red and were almost always a community of color or other marginalized identity.

Redlining began in 1935 when the Home Owner’s Loan Corporation began producing maps of virtually every major city upon request of the Federal Home Loan Bank Board.

Neighborhoods were color coded based on their desirability, from “A - First Grade” to “D - Fourth Grade.” Most often the “D” ranking neighborhoods were black communities, or other communities of minorities, while the “A” ranking neighborhoods were affluent white suburbs.
The maps were used by both public and private banks and loan offices to directly discriminate and refuse loans to residents of the “D” neighborhoods.

The Fair Housing Act of 1968 made discrimination during the process of selling a house illegal, yet redlining was not effectively outlawed until 1977. The Home Mortgage Disclosure Act of 1975 required transparency thus making redlining unfeasible, and was followed by the Community Reinvestment Act of 1977 that finally prohibited it

![Redlining](images\redlining.png)

*A red lined map of Oakland, California, created by Home Owner’s Loan Corporation.*

## Data Source #

In a study of insurance availability in Chicago, the U.S. Commission on Civil Rights attempted to examine charges by several community organizations that insurance companies were redlining their neighborhoods, i.e. canceling policies or refusing to insure or renew.

First the Illinois Department of Insurance provided the number of cancellations, non-renewals, new policies, and renewals of homeowners and residential ﬁre insurance policies by ZIP code for the months of December 1977 through February 1978. The companies that provided this information account for more than 70% of the homeowner’s insurance policies written in the City of Chicago. The department also supplied the number of FAIR plan policies written a renewed in Chicago by zip code for the months of December 1977 through May 1978. Since most FAIR plan policyholders secure such coverage only after they have been rejected by the voluntary market, rather than as a result of a preference for that type of insurance, the distribution of FAIR plan policies is another measure of insurance availability in the voluntary market.

Secondly, the Chicago Police Department provided crime data, by beat, on all thefts for the year 1975. Most Insurance companies claim to base their underwriting activities on loss data from the preceding years, i.e. a 2-3-year lag seems reasonable for analysis purposes. the Chicago Fire Department provided similar data on ﬁres occurring during 1975. These ﬁre and theft data were organized by zip code.

Finally, the US Bureau of the census supplied data on racial composition, income and age and value of residential units for each ZIP code in Chicago. To adjust for these differences in the populations size associated with different ZIP code areas, the theft data were expressed as incidents per 1,000 population and the ﬁre and insurance data as incidents per 100 housing units.

Source: [(here)](https://rdrr.io/cran/faraway/man/chredlin.html).

## Features #

- **race racial:** composition in percent minority
- **fire:** ﬁres per 100 housing units
- **theft:** theft per 1000 population
- **age:** percent of housing units built before 1939
- **volact:** new homeowner policies plus renewals minus cancellations and non-renewals per 100 housing units
- **involact:** new FAIR plan policies and renewals per 100 housing units
- **income:** median family income

## Goal #
To compute the effect of different parameters on insurance redlining in 1975, in which race has been a dominant contributor. To Creating a Linear model for the involuntary market activity variable (the number getting FAIR plan insurance) based on the other parameters. Hence, we can compare the parameters who effects the redlining most in the past vs the one’s which are affecting it now. This regression analysis will give a comparison matric to the policy maker to measure the changes of insurance redlining now and then.  


## Exploratory Data Analysis #
Boxplots show some unusual observations, that we are later going to deal with.
![Outliers](images\boxplot1.png)


## Linear Model Assumptions ##
### Linearity Check
On full model (model with all predictors) I found that all predictors posses linear relationship with response.

![linearity](images\linearity.jpg)
### Normality of Errors 
qqnorm gives fatter tails distribution.
![Normality](images\qqnorm.jpg)

**Shapiro-Wilk normality test:** gives **p-value = 0.6317**. High p-value  favors the null hypotheses that the distribution is normal. 

## Error Variance ##
![Variance](images\errorvarience.jpg)
Looks constant variance with few anomalies.

## Multi-Colinearity ##
Variance Inflation factors:
![VIF](images\vif.jpg)


-----------------


**Brief Description:**
-	Performed regression analysis using (R, ANOVA) for insurance redlining on various neighborhoods of Chicago from 1977 to 1978 based on insurance policies, police departments, and census data.
-	Results can be used as a comparison matrix for the factors affecting redlining (like racial composition), for further analysis of the latest years data.


**Content:**

- R notebook of project (.rmd)
- HTML format notebook
- Report: https://www.slideshare.net/MalikHassanQayyum/chicago-insurance-redlining-report
- Presentation: https://www.slideshare.net/MalikHassanQayyum/chicago-insurance-redlining-presentation

### Course 
**BOOK:** Linear Models with R (Chapman & Hall/CRC Texts in Statistical Science) 2nd Edition<br>
**Professor:** Dr. Ellie Small<br>
<br>
