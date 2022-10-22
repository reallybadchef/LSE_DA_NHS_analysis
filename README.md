# LSE_DA_NHS_analysis
Intro:
project contracted by NHS to analyse the utilisatiohn of services. mainly answering if there has been sufficient staff anc apacity within the primary care networks and what the actual utilisation of resources were.

Importing and exploring the data:
Importing the data, the most crucial aspect was to utilise the correct pandas function to access the data. For instance: the actual_duration and appointments_regional were opened with a pd.read_csv('file_name.csv'), the national_categories file was opened with a pd.read_excel('file_name.xlsx'). Inspected the data by viewing the general data by looking at the first five rows, looked for missing values, viewed the rundown of metadata and finally took a look at the descriptive statistics of each dataframe. This was done by a variety of functions using: dataframe.head(), dataframe[dataframe.isna().any(axis = 1)].shape, dataframe.info() and finally built a function to provide a descriptive statistics of the dataframes depending on the datatype. 
From data, can see there were 106 ICB locations, in which the locations with the highest record of appointments are: North West London ICB, Kent and Medway ICB, Devon ICB, Hampshire and Isle of Wight ICB and the North East London ICB. SHown that there were 5 different service settings, 3 context types, 18 national categories and 3 distinct appointment  statuses.
Wrangling the data:
Q1. changed relevant portions of data to format easier for analysis, utilising pd.to_datetime() on the desired dataframe column. The latest and earliest records in the actual_duration and national categories as shown by utilising the .max() and .min() functions, 30-06-2022 for both and 01-12-2021 the actual_duration and 01-08-2021 the national categories. 
Q2. General Practice-2080, Other-1307, Primary Care Network-1261, Extended Access Provision-1076, Unmapped-150.
Q3. Month witgh the highest number of appointments would be the November of 2021, which had 30405070 appointments.
Q4. 2022-03: 82822, 2021-11: 77652, 2022-05: 77425, 2021-09: 74922, 2022-06: 74168, 2021-10: 74078, 2021-12: 72651, 2022-01: 71896, 2022-02: 71769, 2022-04: 70012, 2021-08: 69999
Visualisations of initial trends:
viewing the monthly aggregates of the different service settings, context types and national categories, it seems that there are common peaks across al areas during November 2021, March 2022 and May 2022. Possibly due to change in weather. Appoointments also commonly drop off june-aug and dec-feb, however not sufficient data to say it would be an annual trend.
Seasonal visulaisations also show common patterns, with no appointments taken on weekends most number of visits on the first working day of the week and slowly drops during the working days. Looking at the axis, the pattern is only a mild correlation across the weeks, in actuality the count of appointment in autum is significantly higher than the other seasons and summer having the lowest count of appoinments booked.

Data scraping:
Based off the unique value counts of retweeted and favourited messages, not much information other than skew of how popular the tweet is can be inferred from those columns. Hence other columns would be required to gain a much more comprehensive understanding.
Overwhelming number of tweets related to healthcare in the uk utilise the #healtcare hashtag(60.1%), but otherwise the other hastags have significantly lower count. Removing the #healthcare hashtag, the visualisation looks muchbetter. top searches have hastags of #health, #medicine, #ai, #jobs and #medical.

Reccomendations:
Q1. max utilisation levels is 84.5%, the big range of fluctuations going from high 50% to mid 80%.
Q2. most of the time the staff type with the most bookings are GPs, however this is very closely correlated to the pattern for other sstaff types, which the peaks for nov 2020 and 2021 surpass for those of GPs. 
Q3. Attendence fulctuates around 20000000 - 25000000 each month, however low attendence of ~14000000 around April 2020. Appointments that were not attended to or had an unkown status were relatively more stable and did not fluctuate as much compared to the attended appointments.
