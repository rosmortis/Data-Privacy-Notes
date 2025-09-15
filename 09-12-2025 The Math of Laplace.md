Differential privacy:
- def
- promise
- diff/good

## The Laplace Mechanism
When we plot the empirical distribution of the Laplace mechanism it looks like this
![[Screenshot 2025-09-12 at 1.28.02 PM.png|400]]
### What does this mean
2.0 Large $\epsilon$ = less noise = less privacy
- Less spread out
1.0 Small  $\epsilon$ = more noise = more privacy
- More spread out
- More likely to get bigger numbers

The blue here is the PDF of the given value, meaning what is the probability that we will get that output.

Why is the noise centered at zero?
1) Most likely outcome is that we add minimal noise
2) nice if the result are unbiased
	1) If we run the thing infinite times and take the average we want it to be the right answer

### Composition
If we do two releases of differentially private data the combination of the two datasets are also differentially private. The total epsilon is the sum of the others.
