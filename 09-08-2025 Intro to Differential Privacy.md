## Finishing $K$-Anonymity
- Generalization
	- Transform data to make it satisfy $k$-Anonymity
		- Increase number of people who have a value
		- Decrease uniqueness
		- Heuristic (difficult)
		- Utility tradeoff
		- Optimal tradeoff is $NP$-Hard 
		- **In practice: Try your best**
- Attacks
	- Homogeneity attack
		- Requires knowledge of targets group
			- e.g no other group exists with targets info
	- Auxiliary data attack
		- Elimination attack
			- We learn about the **other** people in the group and extrapolate out target
		- Close to a linking attack

## Differential Privacy
aggregation + diff privacy 
- much safer
### What is DP
We add random noise to things, creates uncertainty