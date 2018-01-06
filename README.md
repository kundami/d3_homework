# Unit 16 | Assignment - Data Journalism and D3

<a target='_blank' href="https://giphy.com/gifs/newspaper-press-v2xIous7mnEYg"><img alt='Newspaper Printing (via GIPHY)' src="http://i.giphy.com/v2xIous7mnEYg.gif" /> <br><em>via GIPHY</em></a>

## Background

Welcome to the newsroom! You've just accepted a data visualization position for a major metro paper. You're tasked with analyzing the current trends shaping people's lives, as well as creating charts, graphs and interactives to help readers understand your findings.

The editor wants to run a series of feature stories about the health risks facing particular demographics. She's counting on you to sniff out the first story idea by sifting through the latest information from the U.S. Census Bureau and the Behavioral Risk Factor Surveillance System.

The beat reporters will go out and investigate the relationship you find, sourcing experts and finding anecdotes to back up your research. That's tough work, and they won't be happy about digging for a story that doesn't exist—you'll need to find a convincing correlation before you even think about pitching your first article. The editor also wants you to make a scatter plot to show the correlation—you _are_ the data visualizer, after all.

## Your Task

### Level 1: D3 Dabbler

![4-scatter](Images/4-scatter.jpg)

You need to find a correlation between two data variables, each measured state by state and taken from different data sources. You'll then visualize the correlation with a scatter plot and embed the graphic into an .html file. You need to accomplish these four steps.

#### 1. Find the Data

![2-census](Images/2-census.jpg)

Look for demographic information using the 2014 one-year estimates from the U.S. Census Bureau's American Community Survey. You can specify your information using the [American FactFinder](http://factfinder.census.gov/faces/nav/jsf/pages/searchresults.xhtml) tool. When searching through the data, be sure to select these options in the left sidebar:

* Topics -> Dataset -> 2014 ACS 1-year estimates

* Geographies -> Select a geographic type -> State - 040 -> All States within United States and Puerto Rico

When you select those filters, use the search bar to chose the demographic of your choice, or browse through the entries already shown. Click the data that interests you and then download the .csv file.

Next, you'll search for data on health risks using 2014 survey data from the [Behavioral Risk Factor Surveillance System](https://chronicdata.cdc.gov/Behavioral-Risk-Factors/BRFSS-2014-Overall/5ra3-ixqq). Note that we already filtered the data by year and break-out—you just need to find the behavioral risk you want to use. Filter the `Question` data on the site before downloading a specified .csv, or simply download the whole .csv file and use Excel's filtering tools.

![3-brfss](Images/3-brfss.jpg)

#### 2. Format and Test the Data

StateWideImmToNonImmPopluation.ipynb is used to format State Wide data for People Moving in and out of each state.

Hypothesis : The Data Analysis would test the Total Estimate of Local Population for various
Age Categories grouped by Working Age Group and Non Working Age Group defined as following:

Working Population Age > 18 and Age < 64
Non Working Population Age < 18 and Age > 64

and compare the ratio of Working to Non Working  between Local and Immigrant Population.

The analysis found :

1 . There is a strong correlation between Working/Non working ratios within Local Population across states.
    Lower ratios indicate more Non Working Age Group which may translate to less Taxes and more dependence
    on Local Infrastructure


 2. The Immigrant Population has higher Working/Non Working ratios which may translate to more taxes and less
     dependence on Local Infrastuture.   


The following categoories of Migration data was selected for Analysis.

GEO.id	Id
GEO.id2	Id2
GEO.display-label	Geography
HC01_EST_VC01	Total; Estimate; Population 1 year and over
HC01_MOE_VC01	Total; Margin of Error; Population 1 year and over
HC02_EST_VC01	Moved; within same county; Estimate; Population 1 year and over
HC02_MOE_VC01	Moved; within same county; Margin of Error; Population 1 year and over
HC03_EST_VC01	Moved; from different county, same state; Estimate; Population 1 year and over
HC03_MOE_VC01	Moved; from different county, same state; Margin of Error; Population 1 year and over
HC04_EST_VC01	Moved; from different  state; Estimate; Population 1 year and over
HC04_MOE_VC01	Moved; from different  state; Margin of Error; Population 1 year and over
HC05_EST_VC01	Moved; from abroad; Estimate; Population 1 year and over
HC05_MOE_VC01	Moved; from abroad; Margin of Error; Population 1 year and over
HC01_EST_VC03	Total; Estimate; AGE - 1 to 4 years
HC01_MOE_VC03	Total; Margin of Error; AGE - 1 to 4 years
HC02_EST_VC03	Moved; within same county; Estimate; AGE - 1 to 4 years
HC02_MOE_VC03	Moved; within same county; Margin of Error; AGE - 1 to 4 years
HC03_EST_VC03	Moved; from different county, same state; Estimate; AGE - 1 to 4 years
HC03_MOE_VC03	Moved; from different county, same state; Margin of Error; AGE - 1 to 4 years
HC04_EST_VC03	Moved; from different  state; Estimate; AGE - 1 to 4 years
HC04_MOE_VC03	Moved; from different  state; Margin of Error; AGE - 1 to 4 years
HC05_EST_VC03	Moved; from abroad; Estimate; AGE - 1 to 4 years
HC05_MOE_VC03	Moved; from abroad; Margin of Error; AGE - 1 to 4 years
HC01_EST_VC04	Total; Estimate; AGE - 5 to 17 years
HC01_MOE_VC04	Total; Margin of Error; AGE - 5 to 17 years
HC02_EST_VC04	Moved; within same county; Estimate; AGE - 5 to 17 years
HC02_MOE_VC04	Moved; within same county; Margin of Error; AGE - 5 to 17 years
HC03_EST_VC04	Moved; from different county, same state; Estimate; AGE - 5 to 17 years
HC03_MOE_VC04	Moved; from different county, same state; Margin of Error; AGE - 5 to 17 years
HC04_EST_VC04	Moved; from different  state; Estimate; AGE - 5 to 17 years
HC04_MOE_VC04	Moved; from different  state; Margin of Error; AGE - 5 to 17 years
HC05_EST_VC04	Moved; from abroad; Estimate; AGE - 5 to 17 years
HC05_MOE_VC04	Moved; from abroad; Margin of Error; AGE - 5 to 17 years
HC01_EST_VC05	Total; Estimate; AGE - 18 to 24 years
HC01_MOE_VC05	Total; Margin of Error; AGE - 18 to 24 years
HC02_EST_VC05	Moved; within same county; Estimate; AGE - 18 to 24 years
HC02_MOE_VC05	Moved; within same county; Margin of Error; AGE - 18 to 24 years
HC03_EST_VC05	Moved; from different county, same state; Estimate; AGE - 18 to 24 years
HC03_MOE_VC05	Moved; from different county, same state; Margin of Error; AGE - 18 to 24 years
HC04_EST_VC05	Moved; from different  state; Estimate; AGE - 18 to 24 years
HC04_MOE_VC05	Moved; from different  state; Margin of Error; AGE - 18 to 24 years
HC05_EST_VC05	Moved; from abroad; Estimate; AGE - 18 to 24 years
HC05_MOE_VC05	Moved; from abroad; Margin of Error; AGE - 18 to 24 years
HC01_EST_VC06	Total; Estimate; AGE - 25 to 34 years
HC01_MOE_VC06	Total; Margin of Error; AGE - 25 to 34 years
HC02_EST_VC06	Moved; within same county; Estimate; AGE - 25 to 34 years
HC02_MOE_VC06	Moved; within same county; Margin of Error; AGE - 25 to 34 years
HC03_EST_VC06	Moved; from different county, same state; Estimate; AGE - 25 to 34 years
HC03_MOE_VC06	Moved; from different county, same state; Margin of Error; AGE - 25 to 34 years
HC04_EST_VC06	Moved; from different  state; Estimate; AGE - 25 to 34 years
HC04_MOE_VC06	Moved; from different  state; Margin of Error; AGE - 25 to 34 years
HC05_EST_VC06	Moved; from abroad; Estimate; AGE - 25 to 34 years
HC05_MOE_VC06	Moved; from abroad; Margin of Error; AGE - 25 to 34 years
HC01_EST_VC07	Total; Estimate; AGE - 35 to 44 years
HC01_MOE_VC07	Total; Margin of Error; AGE - 35 to 44 years
HC02_EST_VC07	Moved; within same county; Estimate; AGE - 35 to 44 years
HC02_MOE_VC07	Moved; within same county; Margin of Error; AGE - 35 to 44 years
HC03_EST_VC07	Moved; from different county, same state; Estimate; AGE - 35 to 44 years
HC03_MOE_VC07	Moved; from different county, same state; Margin of Error; AGE - 35 to 44 years
HC04_EST_VC07	Moved; from different  state; Estimate; AGE - 35 to 44 years
HC04_MOE_VC07	Moved; from different  state; Margin of Error; AGE - 35 to 44 years
HC05_EST_VC07	Moved; from abroad; Estimate; AGE - 35 to 44 years
HC05_MOE_VC07	Moved; from abroad; Margin of Error; AGE - 35 to 44 years
HC01_EST_VC08	Total; Estimate; AGE - 45 to 54 years
HC01_MOE_VC08	Total; Margin of Error; AGE - 45 to 54 years
HC02_EST_VC08	Moved; within same county; Estimate; AGE - 45 to 54 years
HC02_MOE_VC08	Moved; within same county; Margin of Error; AGE - 45 to 54 years
HC03_EST_VC08	Moved; from different county, same state; Estimate; AGE - 45 to 54 years
HC03_MOE_VC08	Moved; from different county, same state; Margin of Error; AGE - 45 to 54 years
HC04_EST_VC08	Moved; from different  state; Estimate; AGE - 45 to 54 years
HC04_MOE_VC08	Moved; from different  state; Margin of Error; AGE - 45 to 54 years
HC05_EST_VC08	Moved; from abroad; Estimate; AGE - 45 to 54 years
HC05_MOE_VC08	Moved; from abroad; Margin of Error; AGE - 45 to 54 years
HC01_EST_VC09	Total; Estimate; AGE - 55 to 64 years
HC01_MOE_VC09	Total; Margin of Error; AGE - 55 to 64 years
HC02_EST_VC09	Moved; within same county; Estimate; AGE - 55 to 64 years
HC02_MOE_VC09	Moved; within same county; Margin of Error; AGE - 55 to 64 years
HC03_EST_VC09	Moved; from different county, same state; Estimate; AGE - 55 to 64 years
HC03_MOE_VC09	Moved; from different county, same state; Margin of Error; AGE - 55 to 64 years
HC04_EST_VC09	Moved; from different  state; Estimate; AGE - 55 to 64 years
HC04_MOE_VC09	Moved; from different  state; Margin of Error; AGE - 55 to 64 years
HC05_EST_VC09	Moved; from abroad; Estimate; AGE - 55 to 64 years
HC05_MOE_VC09	Moved; from abroad; Margin of Error; AGE - 55 to 64 years
HC01_EST_VC10	Total; Estimate; AGE - 65 to 74 years
HC01_MOE_VC10	Total; Margin of Error; AGE - 65 to 74 years
HC02_EST_VC10	Moved; within same county; Estimate; AGE - 65 to 74 years
HC02_MOE_VC10	Moved; within same county; Margin of Error; AGE - 65 to 74 years
HC03_EST_VC10	Moved; from different county, same state; Estimate; AGE - 65 to 74 years
HC03_MOE_VC10	Moved; from different county, same state; Margin of Error; AGE - 65 to 74 years
HC04_EST_VC10	Moved; from different  state; Estimate; AGE - 65 to 74 years
HC04_MOE_VC10	Moved; from different  state; Margin of Error; AGE - 65 to 74 years
HC05_EST_VC10	Moved; from abroad; Estimate; AGE - 65 to 74 years
HC05_MOE_VC10	Moved; from abroad; Margin of Error; AGE - 65 to 74 years
HC01_EST_VC11	Total; Estimate; AGE - 75 years and over
HC01_MOE_VC11	Total; Margin of Error; AGE - 75 years and over
HC02_EST_VC11	Moved; within same county; Estimate; AGE - 75 years and over
HC02_MOE_VC11	Moved; within same county; Margin of Error; AGE - 75 years and over
HC03_EST_VC11	Moved; from different county, same state; Estimate; AGE - 75 years and over
HC03_MOE_VC11	Moved; from different county, same state; Margin of Error; AGE - 75 years and over
HC04_EST_VC11	Moved; from different  state; Estimate; AGE - 75 years and over
HC04_MOE_VC11	Moved; from different  state; Margin of Error; AGE - 75 years and over
HC05_EST_VC11	Moved; from abroad; Estimate; AGE - 75 years and over
HC05_MOE_VC11	Moved; from abroad; Margin of Error; AGE - 75 years and over
HC01_EST_VC13	Total; Estimate; Median age (years)
HC01_MOE_VC13	Total; Margin of Error; Median age (years)
HC02_EST_VC13	Moved; within same county; Estimate; Median age (years)
HC02_MOE_VC13	Moved; within same county; Margin of Error; Median age (years)
HC03_EST_VC13	Moved; from different county, same state; Estimate; Median age (years)
HC03_MOE_VC13	Moved; from different county, same state; Margin of Error; Median age (years)
HC04_EST_VC13	Moved; from different  state; Estimate; Median age (years)
HC04_MOE_VC13	Moved; from different  state; Margin of Error; Median age (years)
HC05_EST_VC13	Moved; from abroad; Estimate; Median age (years)
HC05_MOE_VC13	Moved; from abroad; Margin of Error; Median age (years)
HC01_EST_VC16	Total; Estimate; SEX - Male
HC01_MOE_VC16	Total; Margin of Error; SEX - Male
HC02_EST_VC16	Moved; within same county; Estimate; SEX - Male
HC02_MOE_VC16	Moved; within same county; Margin of Error; SEX - Male
HC03_EST_VC16	Moved; from different county, same state; Estimate; SEX - Male
HC03_MOE_VC16	Moved; from different county, same state; Margin of Error; SEX - Male
HC04_EST_VC16	Moved; from different  state; Estimate; SEX - Male
HC04_MOE_VC16	Moved; from different  state; Margin of Error; SEX - Male
HC05_EST_VC16	Moved; from abroad; Estimate; SEX - Male
HC05_MOE_VC16	Moved; from abroad; Margin of Error; SEX - Male
HC01_EST_VC17	Total; Estimate; SEX - Female
HC01_MOE_VC17	Total; Margin of Error; SEX - Female
HC02_EST_VC17	Moved; within same county; Estimate; SEX - Female
HC02_MOE_VC17	Moved; within same county; Margin of Error; SEX - Female
HC03_EST_VC17	Moved; from different county, same state; Estimate; SEX - Female
HC03_MOE_VC17	Moved; from different county, same state; Margin of Error; SEX - Female
HC04_EST_VC17	Moved; from different  state; Estimate; SEX - Female
HC04_MOE_VC17	Moved; from different  state; Margin of Error; SEX - Female
HC05_EST_VC17	Moved; from abroad; Estimate; SEX - Female
HC05_MOE_VC17	Moved; from abroad; Margin of Error; SEX - Female
HC01_EST_VC20	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC01_MOE_VC20	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC02_EST_VC20	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC02_MOE_VC20	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC03_EST_VC20	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC03_MOE_VC20	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC04_EST_VC20	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC04_MOE_VC20	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC05_EST_VC20	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC05_MOE_VC20	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race
HC01_EST_VC21	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC01_MOE_VC21	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC02_EST_VC21	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC02_MOE_VC21	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC03_EST_VC21	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC03_MOE_VC21	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC04_EST_VC21	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC04_MOE_VC21	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC05_EST_VC21	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC05_MOE_VC21	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - White
HC01_EST_VC22	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC01_MOE_VC22	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC02_EST_VC22	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC02_MOE_VC22	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC03_EST_VC22	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC03_MOE_VC22	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC04_EST_VC22	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC04_MOE_VC22	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC05_EST_VC22	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC05_MOE_VC22	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Black or African American
HC01_EST_VC23	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC01_MOE_VC23	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC02_EST_VC23	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC02_MOE_VC23	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC03_EST_VC23	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC03_MOE_VC23	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC04_EST_VC23	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC04_MOE_VC23	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC05_EST_VC23	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC05_MOE_VC23	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - American Indian and Alaska Native
HC01_EST_VC24	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC01_MOE_VC24	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC02_EST_VC24	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC02_MOE_VC24	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC03_EST_VC24	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC03_MOE_VC24	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC04_EST_VC24	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC04_MOE_VC24	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC05_EST_VC24	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC05_MOE_VC24	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Asian
HC01_EST_VC25	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC01_MOE_VC25	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC02_EST_VC25	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC02_MOE_VC25	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC03_EST_VC25	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC03_MOE_VC25	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC04_EST_VC25	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC04_MOE_VC25	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC05_EST_VC25	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC05_MOE_VC25	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Native Hawaiian and Other Pacific Islander
HC01_EST_VC26	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC01_MOE_VC26	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC02_EST_VC26	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC02_MOE_VC26	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC03_EST_VC26	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC03_MOE_VC26	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC04_EST_VC26	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC04_MOE_VC26	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC05_EST_VC26	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC05_MOE_VC26	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - One race - Some other race
HC01_EST_VC27	Total; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC01_MOE_VC27	Total; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC02_EST_VC27	Moved; within same county; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC02_MOE_VC27	Moved; within same county; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC03_EST_VC27	Moved; from different county, same state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC03_MOE_VC27	Moved; from different county, same state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC04_EST_VC27	Moved; from different  state; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC04_MOE_VC27	Moved; from different  state; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC05_EST_VC27	Moved; from abroad; Estimate; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC05_MOE_VC27	Moved; from abroad; Margin of Error; RACE AND HISPANIC OR LATINO ORIGIN - Two or more races
HC01_EST_VC29	Total; Estimate; Hispanic or Latino origin (of any race)
HC01_MOE_VC29	Total; Margin of Error; Hispanic or Latino origin (of any race)
HC02_EST_VC29	Moved; within same county; Estimate; Hispanic or Latino origin (of any race)
HC02_MOE_VC29	Moved; within same county; Margin of Error; Hispanic or Latino origin (of any race)
HC03_EST_VC29	Moved; from different county, same state; Estimate; Hispanic or Latino origin (of any race)
HC03_MOE_VC29	Moved; from different county, same state; Margin of Error; Hispanic or Latino origin (of any race)
HC04_EST_VC29	Moved; from different  state; Estimate; Hispanic or Latino origin (of any race)
HC04_MOE_VC29	Moved; from different  state; Margin of Error; Hispanic or Latino origin (of any race)
HC05_EST_VC29	Moved; from abroad; Estimate; Hispanic or Latino origin (of any race)
HC05_MOE_VC29	Moved; from abroad; Margin of Error; Hispanic or Latino origin (of any race)
HC01_EST_VC30	Total; Estimate; White alone, not Hispanic or Latino
HC01_MOE_VC30	Total; Margin of Error; White alone, not Hispanic or Latino
HC02_EST_VC30	Moved; within same county; Estimate; White alone, not Hispanic or Latino
HC02_MOE_VC30	Moved; within same county; Margin of Error; White alone, not Hispanic or Latino
HC03_EST_VC30	Moved; from different county, same state; Estimate; White alone, not Hispanic or Latino
HC03_MOE_VC30	Moved; from different county, same state; Margin of Error; White alone, not Hispanic or Latino
HC04_EST_VC30	Moved; from different  state; Estimate; White alone, not Hispanic or Latino
HC04_MOE_VC30	Moved; from different  state; Margin of Error; White alone, not Hispanic or Latino
HC05_EST_VC30	Moved; from abroad; Estimate; White alone, not Hispanic or Latino
HC05_MOE_VC30	Moved; from abroad; Margin of Error; White alone, not Hispanic or Latino
HC01_EST_VC33	Total; Estimate; NATIVITY AND CITIZENSHIP STATUS - Native
HC01_MOE_VC33	Total; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Native
HC02_EST_VC33	Moved; within same county; Estimate; NATIVITY AND CITIZENSHIP STATUS - Native
HC02_MOE_VC33	Moved; within same county; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Native
HC03_EST_VC33	Moved; from different county, same state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Native
HC03_MOE_VC33	Moved; from different county, same state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Native
HC04_EST_VC33	Moved; from different  state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Native
HC04_MOE_VC33	Moved; from different  state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Native
HC05_EST_VC33	Moved; from abroad; Estimate; NATIVITY AND CITIZENSHIP STATUS - Native
HC05_MOE_VC33	Moved; from abroad; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Native
HC01_EST_VC34	Total; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC01_MOE_VC34	Total; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC02_EST_VC34	Moved; within same county; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC02_MOE_VC34	Moved; within same county; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC03_EST_VC34	Moved; from different county, same state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC03_MOE_VC34	Moved; from different county, same state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC04_EST_VC34	Moved; from different  state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC04_MOE_VC34	Moved; from different  state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC05_EST_VC34	Moved; from abroad; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC05_MOE_VC34	Moved; from abroad; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born
HC01_EST_VC35	Total; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC01_MOE_VC35	Total; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC02_EST_VC35	Moved; within same county; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC02_MOE_VC35	Moved; within same county; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC03_EST_VC35	Moved; from different county, same state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC03_MOE_VC35	Moved; from different county, same state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC04_EST_VC35	Moved; from different  state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC04_MOE_VC35	Moved; from different  state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC05_EST_VC35	Moved; from abroad; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC05_MOE_VC35	Moved; from abroad; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Naturalized U.S. citizen
HC01_EST_VC36	Total; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC01_MOE_VC36	Total; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC02_EST_VC36	Moved; within same county; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC02_MOE_VC36	Moved; within same county; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC03_EST_VC36	Moved; from different county, same state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC03_MOE_VC36	Moved; from different county, same state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC04_EST_VC36	Moved; from different  state; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC04_MOE_VC36	Moved; from different  state; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC05_EST_VC36	Moved; from abroad; Estimate; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC05_MOE_VC36	Moved; from abroad; Margin of Error; NATIVITY AND CITIZENSHIP STATUS - Foreign born - Not a U.S. citizen
HC01_EST_VC39	Total; Estimate; MARITAL STATUS - Population 15 years and over
HC01_MOE_VC39	Total; Margin of Error; MARITAL STATUS - Population 15 years and over
HC02_EST_VC39	Moved; within same county; Estimate; MARITAL STATUS - Population 15 years and over
HC02_MOE_VC39	Moved; within same county; Margin of Error; MARITAL STATUS - Population 15 years and over
HC03_EST_VC39	Moved; from different county, same state; Estimate; MARITAL STATUS - Population 15 years and over
HC03_MOE_VC39	Moved; from different county, same state; Margin of Error; MARITAL STATUS - Population 15 years and over
HC04_EST_VC39	Moved; from different  state; Estimate; MARITAL STATUS - Population 15 years and over
HC04_MOE_VC39	Moved; from different  state; Margin of Error; MARITAL STATUS - Population 15 years and over
HC05_EST_VC39	Moved; from abroad; Estimate; MARITAL STATUS - Population 15 years and over
HC05_MOE_VC39	Moved; from abroad; Margin of Error; MARITAL STATUS - Population 15 years and over
HC01_EST_VC40	Total; Estimate; MARITAL STATUS - Population 15 years and over - Never married
HC01_MOE_VC40	Total; Margin of Error; MARITAL STATUS - Population 15 years and over - Never married
HC02_EST_VC40	Moved; within same county; Estimate; MARITAL STATUS - Population 15 years and over - Never married
HC02_MOE_VC40	Moved; within same county; Margin of Error; MARITAL STATUS - Population 15 years and over - Never married
HC03_EST_VC40	Moved; from different county, same state; Estimate; MARITAL STATUS - Population 15 years and over - Never married
HC03_MOE_VC40	Moved; from different county, same state; Margin of Error; MARITAL STATUS - Population 15 years and over - Never married
HC04_EST_VC40	Moved; from different  state; Estimate; MARITAL STATUS - Population 15 years and over - Never married
HC04_MOE_VC40	Moved; from different  state; Margin of Error; MARITAL STATUS - Population 15 years and over - Never married
HC05_EST_VC40	Moved; from abroad; Estimate; MARITAL STATUS - Population 15 years and over - Never married
HC05_MOE_VC40	Moved; from abroad; Margin of Error; MARITAL STATUS - Population 15 years and over - Never married
HC01_EST_VC41	Total; Estimate; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC01_MOE_VC41	Total; Margin of Error; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC02_EST_VC41	Moved; within same county; Estimate; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC02_MOE_VC41	Moved; within same county; Margin of Error; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC03_EST_VC41	Moved; from different county, same state; Estimate; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC03_MOE_VC41	Moved; from different county, same state; Margin of Error; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC04_EST_VC41	Moved; from different  state; Estimate; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC04_MOE_VC41	Moved; from different  state; Margin of Error; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC05_EST_VC41	Moved; from abroad; Estimate; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC05_MOE_VC41	Moved; from abroad; Margin of Error; MARITAL STATUS - Population 15 years and over - Now married, except separated
HC01_EST_VC42	Total; Estimate; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC01_MOE_VC42	Total; Margin of Error; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC02_EST_VC42	Moved; within same county; Estimate; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC02_MOE_VC42	Moved; within same county; Margin of Error; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC03_EST_VC42	Moved; from different county, same state; Estimate; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC03_MOE_VC42	Moved; from different county, same state; Margin of Error; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC04_EST_VC42	Moved; from different  state; Estimate; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC04_MOE_VC42	Moved; from different  state; Margin of Error; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC05_EST_VC42	Moved; from abroad; Estimate; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC05_MOE_VC42	Moved; from abroad; Margin of Error; MARITAL STATUS - Population 15 years and over - Divorced or separated
HC01_EST_VC43	Total; Estimate; MARITAL STATUS - Population 15 years and over - Widowed
HC01_MOE_VC43	Total; Margin of Error; MARITAL STATUS - Population 15 years and over - Widowed
HC02_EST_VC43	Moved; within same county; Estimate; MARITAL STATUS - Population 15 years and over - Widowed
HC02_MOE_VC43	Moved; within same county; Margin of Error; MARITAL STATUS - Population 15 years and over - Widowed
HC03_EST_VC43	Moved; from different county, same state; Estimate; MARITAL STATUS - Population 15 years and over - Widowed
HC03_MOE_VC43	Moved; from different county, same state; Margin of Error; MARITAL STATUS - Population 15 years and over - Widowed
HC04_EST_VC43	Moved; from different  state; Estimate; MARITAL STATUS - Population 15 years and over - Widowed
HC04_MOE_VC43	Moved; from different  state; Margin of Error; MARITAL STATUS - Population 15 years and over - Widowed
HC05_EST_VC43	Moved; from abroad; Estimate; MARITAL STATUS - Population 15 years and over - Widowed
HC05_MOE_VC43	Moved; from abroad; Margin of Error; MARITAL STATUS - Population 15 years and over - Widowed
HC01_EST_VC46	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC01_MOE_VC46	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC02_EST_VC46	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC02_MOE_VC46	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC03_EST_VC46	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC03_MOE_VC46	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC04_EST_VC46	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC04_MOE_VC46	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC05_EST_VC46	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC05_MOE_VC46	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over
HC01_EST_VC47	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC01_MOE_VC47	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC02_EST_VC47	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC02_MOE_VC47	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC03_EST_VC47	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC03_MOE_VC47	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC04_EST_VC47	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC04_MOE_VC47	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC05_EST_VC47	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC05_MOE_VC47	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Less than high school graduate
HC01_EST_VC48	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC01_MOE_VC48	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC02_EST_VC48	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC02_MOE_VC48	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC03_EST_VC48	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC03_MOE_VC48	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC04_EST_VC48	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC04_MOE_VC48	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC05_EST_VC48	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC05_MOE_VC48	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - High school graduate (includes equivalency)
HC01_EST_VC49	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC01_MOE_VC49	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC02_EST_VC49	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC02_MOE_VC49	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC03_EST_VC49	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC03_MOE_VC49	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC04_EST_VC49	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC04_MOE_VC49	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC05_EST_VC49	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC05_MOE_VC49	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Some college or associate's degree
HC01_EST_VC50	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC01_MOE_VC50	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC02_EST_VC50	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC02_MOE_VC50	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC03_EST_VC50	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC03_MOE_VC50	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC04_EST_VC50	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC04_MOE_VC50	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC05_EST_VC50	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC05_MOE_VC50	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Bachelor's degree
HC01_EST_VC51	Total; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC01_MOE_VC51	Total; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC02_EST_VC51	Moved; within same county; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC02_MOE_VC51	Moved; within same county; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC03_EST_VC51	Moved; from different county, same state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC03_MOE_VC51	Moved; from different county, same state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC04_EST_VC51	Moved; from different  state; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC04_MOE_VC51	Moved; from different  state; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC05_EST_VC51	Moved; from abroad; Estimate; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC05_MOE_VC51	Moved; from abroad; Margin of Error; EDUCATIONAL ATTAINMENT - Population 25 years and over - Graduate or professional degree
HC01_EST_VC54	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC01_MOE_VC54	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC02_EST_VC54	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC02_MOE_VC54	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC03_EST_VC54	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC03_MOE_VC54	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC04_EST_VC54	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC04_MOE_VC54	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC05_EST_VC54	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC05_MOE_VC54	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over
HC01_EST_VC55	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC01_MOE_VC55	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC02_EST_VC55	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC02_MOE_VC55	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC03_EST_VC55	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC03_MOE_VC55	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC04_EST_VC55	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC04_MOE_VC55	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC05_EST_VC55	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC05_MOE_VC55	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $1 to $9,999 or loss
HC01_EST_VC56	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC01_MOE_VC56	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC02_EST_VC56	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC02_MOE_VC56	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC03_EST_VC56	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC03_MOE_VC56	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC04_EST_VC56	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC04_MOE_VC56	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC05_EST_VC56	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC05_MOE_VC56	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $10,000 to $14,999
HC01_EST_VC57	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC01_MOE_VC57	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC02_EST_VC57	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC02_MOE_VC57	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC03_EST_VC57	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC03_MOE_VC57	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC04_EST_VC57	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC04_MOE_VC57	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC05_EST_VC57	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC05_MOE_VC57	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $15,000 to $24,999
HC01_EST_VC58	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC01_MOE_VC58	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC02_EST_VC58	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC02_MOE_VC58	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC03_EST_VC58	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC03_MOE_VC58	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC04_EST_VC58	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC04_MOE_VC58	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC05_EST_VC58	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC05_MOE_VC58	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $25,000 to $34,999
HC01_EST_VC59	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC01_MOE_VC59	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC02_EST_VC59	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC02_MOE_VC59	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC03_EST_VC59	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC03_MOE_VC59	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC04_EST_VC59	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC04_MOE_VC59	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC05_EST_VC59	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC05_MOE_VC59	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $35,000 to $49,999
HC01_EST_VC60	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC01_MOE_VC60	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC02_EST_VC60	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC02_MOE_VC60	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC03_EST_VC60	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC03_MOE_VC60	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC04_EST_VC60	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC04_MOE_VC60	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC05_EST_VC60	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC05_MOE_VC60	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $50,000 to $64,999
HC01_EST_VC61	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC01_MOE_VC61	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC02_EST_VC61	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC02_MOE_VC61	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC03_EST_VC61	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC03_MOE_VC61	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC04_EST_VC61	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC04_MOE_VC61	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC05_EST_VC61	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC05_MOE_VC61	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $65,000 to $74,999
HC01_EST_VC62	Total; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC01_MOE_VC62	Total; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC02_EST_VC62	Moved; within same county; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC02_MOE_VC62	Moved; within same county; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC03_EST_VC62	Moved; from different county, same state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC03_MOE_VC62	Moved; from different county, same state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC04_EST_VC62	Moved; from different  state; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC04_MOE_VC62	Moved; from different  state; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC05_EST_VC62	Moved; from abroad; Estimate; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC05_MOE_VC62	Moved; from abroad; Margin of Error; INDIVIDUAL INCOME IN THE PAST 12 MONTHS (IN 2014 INFLATION-ADJUSTED DOLLARS) - Population 15 years and over - $75,000 or more
HC01_EST_VC64	Total; Estimate; Median income (dollars)
HC01_MOE_VC64	Total; Margin of Error; Median income (dollars)
HC02_EST_VC64	Moved; within same county; Estimate; Median income (dollars)
HC02_MOE_VC64	Moved; within same county; Margin of Error; Median income (dollars)
HC03_EST_VC64	Moved; from different county, same state; Estimate; Median income (dollars)
HC03_MOE_VC64	Moved; from different county, same state; Margin of Error; Median income (dollars)
HC04_EST_VC64	Moved; from different  state; Estimate; Median income (dollars)
HC04_MOE_VC64	Moved; from different  state; Margin of Error; Median income (dollars)
HC05_EST_VC64	Moved; from abroad; Estimate; Median income (dollars)
HC05_MOE_VC64	Moved; from abroad; Margin of Error; Median income (dollars)
HC01_EST_VC67	Total; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC01_MOE_VC67	Total; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC02_EST_VC67	Moved; within same county; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC02_MOE_VC67	Moved; within same county; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC03_EST_VC67	Moved; from different county, same state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC03_MOE_VC67	Moved; from different county, same state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC04_EST_VC67	Moved; from different  state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC04_MOE_VC67	Moved; from different  state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC05_EST_VC67	Moved; from abroad; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC05_MOE_VC67	Moved; from abroad; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined
HC01_EST_VC68	Total; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC01_MOE_VC68	Total; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC02_EST_VC68	Moved; within same county; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC02_MOE_VC68	Moved; within same county; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC03_EST_VC68	Moved; from different county, same state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC03_MOE_VC68	Moved; from different county, same state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC04_EST_VC68	Moved; from different  state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC04_MOE_VC68	Moved; from different  state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC05_EST_VC68	Moved; from abroad; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC05_MOE_VC68	Moved; from abroad; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - Below 100 percent of the poverty level
HC01_EST_VC69	Total; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC01_MOE_VC69	Total; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC02_EST_VC69	Moved; within same county; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC02_MOE_VC69	Moved; within same county; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC03_EST_VC69	Moved; from different county, same state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC03_MOE_VC69	Moved; from different county, same state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC04_EST_VC69	Moved; from different  state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC04_MOE_VC69	Moved; from different  state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC05_EST_VC69	Moved; from abroad; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC05_MOE_VC69	Moved; from abroad; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - 100 to 149 percent of the poverty level
HC01_EST_VC70	Total; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC01_MOE_VC70	Total; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC02_EST_VC70	Moved; within same county; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC02_MOE_VC70	Moved; within same county; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC03_EST_VC70	Moved; from different county, same state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC03_MOE_VC70	Moved; from different county, same state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC04_EST_VC70	Moved; from different  state; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC04_MOE_VC70	Moved; from different  state; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC05_EST_VC70	Moved; from abroad; Estimate; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC05_MOE_VC70	Moved; from abroad; Margin of Error; POVERTY STATUS IN THE PAST 12 MONTHS - Population 1 year and over for whom poverty status is determined - At or above 150 percent of the poverty level
HC01_EST_VC73	Total; Estimate; HOUSING TENURE - Population 1 year and over in housing units
HC01_MOE_VC73	Total; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units
HC02_EST_VC73	Moved; within same county; Estimate; HOUSING TENURE - Population 1 year and over in housing units
HC02_MOE_VC73	Moved; within same county; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units
HC03_EST_VC73	Moved; from different county, same state; Estimate; HOUSING TENURE - Population 1 year and over in housing units
HC03_MOE_VC73	Moved; from different county, same state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units
HC04_EST_VC73	Moved; from different  state; Estimate; HOUSING TENURE - Population 1 year and over in housing units
HC04_MOE_VC73	Moved; from different  state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units
HC05_EST_VC73	Moved; from abroad; Estimate; HOUSING TENURE - Population 1 year and over in housing units
HC05_MOE_VC73	Moved; from abroad; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units
HC01_EST_VC74	Total; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC01_MOE_VC74	Total; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC02_EST_VC74	Moved; within same county; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC02_MOE_VC74	Moved; within same county; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC03_EST_VC74	Moved; from different county, same state; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC03_MOE_VC74	Moved; from different county, same state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC04_EST_VC74	Moved; from different  state; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC04_MOE_VC74	Moved; from different  state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC05_EST_VC74	Moved; from abroad; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC05_MOE_VC74	Moved; from abroad; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in owner-occupied housing units
HC01_EST_VC75	Total; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC01_MOE_VC75	Total; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC02_EST_VC75	Moved; within same county; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC02_MOE_VC75	Moved; within same county; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC03_EST_VC75	Moved; from different county, same state; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC03_MOE_VC75	Moved; from different county, same state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC04_EST_VC75	Moved; from different  state; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC04_MOE_VC75	Moved; from different  state; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC05_EST_VC75	Moved; from abroad; Estimate; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC05_MOE_VC75	Moved; from abroad; Margin of Error; HOUSING TENURE - Population 1 year and over in housing units - Householder lived in renter-occupied housing units
HC01_EST_VC78	Total; Estimate; PERCENT IMPUTED - Residence 1 year ago
HC01_MOE_VC78	Total; Margin of Error; PERCENT IMPUTED - Residence 1 year ago
HC02_EST_VC78	Moved; within same county; Estimate; PERCENT IMPUTED - Residence 1 year ago
HC02_MOE_VC78	Moved; within same county; Margin of Error; PERCENT IMPUTED - Residence 1 year ago
HC03_EST_VC78	Moved; from different county, same state; Estimate; PERCENT IMPUTED - Residence 1 year ago
HC03_MOE_VC78	Moved; from different county, same state; Margin of Error; PERCENT IMPUTED - Residence 1 year ago
HC04_EST_VC78	Moved; from different  state; Estimate; PERCENT IMPUTED - Residence 1 year ago
HC04_MOE_VC78	Moved; from different  state; Margin of Error; PERCENT IMPUTED - Residence 1 year ago
HC05_EST_VC78	Moved; from abroad; Estimate; PERCENT IMPUTED - Residence 1 year ago
HC05_MOE_VC78	Moved; from abroad; Margin of Error; PERCENT IMPUTED - Residence 1 year ago
