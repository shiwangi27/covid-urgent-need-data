# covid-urgent-need-data
This repo consists of the Twitter statuses data asking for urgent need help and resource availability data.

*Disclaimer: This is purely data scraping from Twitter, the availability of resources are not verified.* 

The data consists of the following:

- Resources Available
- Urgent Needs 

Currently, the tweet status data is pulled and filtered for May 1 for Mumbai and Delhi. Other cities to follow. The location is actually user's location and not the location of patients or resources (it can be all over the country). 


## Covid India Cases and Vaccination Resources

| Data Source |	Link |	Additonal Link |
| :----------- | :------------: | ---------------: |
|State Wise Vaccination Data	| https://www.mygov.in/covid-19/	| https://www.mohfw.gov.in/pdf/CumulativeCOVIDVaccinationCoverageReport1stMay2021.pdf |
|JHU State Wise	        | https://github.com/CSSEGISandData/COVID-19/tree/master/csse_covid_19_data	| |
|GrainMart District Wise Cases | https://www.grainmart.in/news/covid-19-coronavirus-india-state-and-district-wise-tally/ | |	
|MOHFW State Wise Cases	| https://www.mohfw.gov.in/	| |
|District Wise Cases API	| https://api.covid19india.org/documentation/csv/	| https://coronaclusters.in/ |
|State Wise Covid Facilities	| https://www.mohfw.gov.in/pdf/StatewiseCovidHospitalslink19062020.pdf	| |


More Data Resource Links State wise: 

- [Google Drive State Reports and Dashboards Links](https://docs.google.com/spreadsheets/d/1IOv61NoJ9jOfBXxarxK2vHU3BqIYklY-qFWfXf_CVLQ/edit?usp=sharing)


## Data Fields 

```
    status_id: str
    created_at: str
    text: str
    iso_language_code: str
    location: str
    keyword_matches: List[str]
    user_id: str
    screen_name: str
    followers_count: int
    friends_count: int
    statuses_count: int
    retweet_count: int
    favorite_count: int
    hashtags: List[str]
    datetime: datetime64[ns, UTC]
    date: datetime.date
    urgent_need_flag: bool 
    resource_flag: bool    
```

## A little more on the data

The tweet data is pulled based on Search Query like `oxygen plasma ICU beds ventilator -filter:retweet` minus the retweets (we dont want the same statuses). The other filters are date (past 7 days), geo location with radius in kms (e.g. lat, lon, 16kms), language and most recent tweets. 





