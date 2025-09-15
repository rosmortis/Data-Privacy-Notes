k-anonymity is a method by which we "blend people into the crowd"
## Definition
We say that a dataset is $k$-Anonymized for a particular $k$ if each individual is a member of group size at least $k$. Meaning the data has enough of a population to ensure that all differencing attack can not occur.

## Checking for K-Anonymity
This is easiest to show with a small dataset. This contains age plus two test scores; it clearly dont satisfy $k$-anonymity for $K > 1$. Note that any dataset trivially satisfies $k$-anonymity for $k=1$, since each row can form its own group of size one. 

```Data
   age preTestScore postTestScore 
0   42            4            25 
1   52           24            94
2   36           31            57 
3   24            2            62 
4   73            3            70
```

The above is not k-Anonymous as there are no two identical rows. If we attempted to aggregate this data based on age there would be no change in how unique each individual is.

## Generalizing Data to Satisfy $k$-Anonymity
The process of modifying data to satisfy $k$-anonymity is rather simple we can round things like age, or remove the first digits of a zip code. Upon aggregation we find that the groups of individuals are then larger than they were prior to generalization. This would look something like this: 

```Data
   age preTestScore postTestScore 
0   40            0            20 
1   50           20            90
2   30           30            50 
3   20            2            60 
4   70            3            70
```

Note that this still does not satisfy $k$-anonymity where $k = 2$ however if we attempt to generalize again we will loose all the data.

## Does more Data Improve Generalization
