
| Defenses          | Uncertainty                            | Attacks                            |
| ----------------- | -------------------------------------- | ---------------------------------- |
| DE-Identifycation | removing cols, no unique ID            | linkage attacks                    |
| Aggreation        | reducing groups to one number          | 1) Small groups<br>2) differencing |
| K-anonimity       | Generizlation to ensure non-uniqueness |                                    |
Uncertainty comes from the data
- We are not introducing any new uncertainty
- Like if you share a birthday, then there is some uncertainty
- This means that the uncertainty is bounded by the data itself

Why can we do differencing attacks, how is this allowed
- imagine an interactive query system
- you can only do aggregation queries on the system (so that its safe)
- The data is not safe in this case
- As a matter of fact this is common place in the world where the release of data is mandated
	- Though it is often vetted by a human