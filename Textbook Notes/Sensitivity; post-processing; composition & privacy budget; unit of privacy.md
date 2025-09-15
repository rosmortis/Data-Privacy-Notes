## Define sensitivity
### Global Sensitivity
The amount of noise necessary for DP is defined by the sensitivity of the query that is the amount the answer changes when the input changes. As discussed before two datasets are neighbors if they differ by exactly one data point. We define these sets as $x$ and $x\prime$ in terms of the definition that means that $f(x)$ and $f(x\prime)$ will differ by no more than $GS(f).$ This is a measure of global sensitivity because it is independent of the data. 
### Distance
Distance is defined as the difference between two sets. This can be trivial like with the census or very non-trivial like in the case of location trajectories. Mathematically this is defined as the _symmetric difference_ between the two datasets.
$$
D(x,x\prime) = |(x - x\prime) \cup (x\prime - x)|
$$
Notes on the implications of this definition:
- If $x\prime$ is constructed from $x$ by adding one row then $d(x, x\prime) = 1$
- If $x\prime$ is constructed from $x$ by removing one row then $d(x, x\prime) = 1$
- If $x\prime$ is constructed from $x$ by modifying one row then $d(x, x\prime) = 2$
There are other definitions of distance that result in a neighboring dataset if we modify a row but here we will use this definition. 
## Find the sensitivity of counting queries
## Find the sensitivity of summation queries
## Decompose average queries into counting and summation queries
## Use clipping to bound the sensitivity of summation queries