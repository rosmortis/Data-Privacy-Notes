PII $\to$ DEID
row (match on linking attribute) row
sometimes finds all possible rows that match which is why we will see more rows than in the data
Is a common thing, SQL it is join command

## K-Anonymity
| Defenses          | Uncertainty                            | Attacks                            |
| ----------------- | -------------------------------------- | ---------------------------------- |
| DE-Identifycation | removing cols, no unique ID            | linkage attacks                    |
| Aggreation        | reducing groups to one number          | 1) Small groups<br>2) differencing |
| K-anonymity       | Generizlation to ensure non-uniqueness |                                    |
The solution Anonymity offers is to force non-uniqueness for combinations. 

> [!def]
>  Data satisfies k-anon if:
> 	1) Group all rows by quasi-identifiers
> 	2) All groups have at least $k$ rows

## Quasi-identifiers
What is a quasi-identifier?
- A category in the data that is "somewhat identifying"
Though there is no such thing as a 'non-identifier' so everything is a _QI_ (duh)
We pick values for $k$ that "sound good"