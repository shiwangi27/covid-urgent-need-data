# covid-urgent-need-data
This repo consists of the Twitter statuses data asking for urgent need help and resource availability data.

*Disclaimer: This is purely data scraping from Twitter, the availability of resources are not verified.* 

The data consists of the following:

- Resources Available
- Urgent Needs 

Currently, the tweet status data is pulled and filtered for May 1 for Mumbai and Delhi. Other cities to follow. The location is actually user's location and not the location of patients or resources (it can be all over the country). 


Hope this helps track ad-hoc resource availability for people in need. 



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





