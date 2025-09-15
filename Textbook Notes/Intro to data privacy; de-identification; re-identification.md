## Introduction 
1. Analyze data to learn about the population
	1. Utility
	2. Societal good
	3. Money
2. Prevent learning about individuals
	1. Privacy

## HIPAA
- HIPAA was designed to allow health insurance to transfer between jobs.
- somehow it became the standard for defining PIID
 - The HIPAA safe harbor laws are written in the law, states the 15 things that are mandatory to remove.
	 - https://www.law.cornell.edu/cfr/text/45/164.514
- If you remove these things and something bad happens you can not be sued, henese the name safe harbor. Though this is only applicable to health
	- https://www.hhs.gov/hipaa/for-professionals/covered-entities/index.html
- Though it still remains the "de-facto" standard

## DEID Standards
- **Is there a motion to make a better list for all companies?**
	- No, there is too much money involved
	- There is also no way to make a list, its specific to each company and data set
- **Should this data just not be stored?**
	- Yeah, basically to protect against data breaches
	- And internal sharing
- A case can be made that all Data is identifiable
	- Your ID can be extrapolated from seemly Un-identifiable information
- https://aboutmyinfo.org/
	- scary 

## REID
- You can re-identify ppl from a DEID data set
- Taxi trips in NYC
- Data set released that shows start times end time and how much they paid
- Some guy figured out where celebrities were going by looking at paparazzi photos
- People have been operating on the idea the DEID works well
	- This paper makes the case that that assumption is beginning to break down
	- We should in-fact not rely on DEID at all
	- https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1450006
- This paper makes the opposite case
	- https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2076397
- Joe Agrees with the first guy
- Latina Sweeney (A grad student at the time) took a DEID data set of medical records and found the governors info, then she emailed it to him and they stopped releasing the data
- Ofc its particularly easy to re-identify outliers or people who make more money or are the only people living in a certain zip code.
	- Jeff Bezos
	- The Gov of Mass

## Linkage Attack
A linkage attack is when we link data back to its owner through external means and/or queries. We used to worry about data from one person, there is so much data now.
## 3.4 Aggregation
### Problems of Small Groups
One way to prevent the release of PIID is to only release the aggregated data. These are usually broken down into smaller groups like education and age. Which could look like this:

|     | Education | Age    |
| --- | --------- | ------ |
| 0   | 10th      | 42.032 |
| 1   | 11th      | 42.054 |
| 2   | 12th      | 41.879 |
This, as you would imagine this makes it harder to identify an individuals contribution to the Data as a whole. That is unless we are aggregating a group with only one individual in it, that would provide no privacy at all.

The US census does exactly this, it releases statistics at the block level. This means that its actually not uncommon for PIID to be released this way. 

### Differencing Attacks
It gets worse than that, when we have multiple aggregations released from the same data. If we can sum all the ages in the data set and get say `1360238` for the sum of all ages in the data set. Then we sum the data again but this time excluding our target, and we get `1360182` then determining the age of our target becomes as easy as subtracting the two values from each other `1360238 - 1360182 = 56` 

### On Malicious Queries
An important note is that ALL queries over data should be treated the same. There is no one query that we can assume is safe and private. There is also no way to determine if a query is a part of a larger scheme to extrapolate PIID. As such all queries are treated the same.