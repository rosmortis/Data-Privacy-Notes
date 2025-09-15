## What is Differential Privacy
Differential Privacy is a formal notion of data privacy which means it is a definite quantity. However unlike $k\text{-Anonymity}$ differential privacy is a property of algorithms not data. Meaning we can prove that an algo does it and thus we can prove what it does to data. 

**Note:** Two datasets are considered neighbors if they differ in data by a single individual

## The Privacy Parameter $\epsilon$
The parameter $\epsilon$ is provides a 'knob' to tune the amount of privacy.

The important idea here is that the data will remain the same with or without the data from one individual. Like if we run the algo on $x$ and on $x\prime$ (neighboring datasets) the output will be the same.
## The Laplace Mechanism to Enforce Privacy Counting Queries
Differential privacy is typically used to answer specific queries, lets say this is the query we want to run:

```python
adult[adult['Age'] >= 40].shape[0]
```
`17450`

The easiest way to satisfy differential privacy is then to add some random noise to the data. The key here is to add just enough noise that we don't sacrifice the utility of the data. The mechanism to do this has all ready been developed it is called the Laplace mechanism

### Definition of the Laplace Mechanism
According to the Laplace mechanism, for a function $f(x)$ which returns a number, the following definition of $F(x)$ satisfies $\epsilon$-differential privacy:
$$F(x) = f(x) + lap\bigg({s\over \epsilon}\bigg)$$
Where $s$ is the sensitivity of $f$ and $lap(s)$ denotes sampling from the Laplace distribution with center 0 and scale $s$. The PDF of the Laplace distribution is
$$f(x) = {1\over2S} exp\bigg(-{|x|\over S}\bigg)$$
The global sensitivity of a function $f$ is then defined as the maximum amount its output can change between any pair of adjacent datasets. A complex topic but integral to defining differential privacy. For now all we need to know is that counting queries will always have a sensitivity of one. This means that we will use Laplace with a sensitivity of one and any epsilon of out choosing. To do this we must leverage NumPy's `Random laplace`

```python
sensitivity = 1
epesilon = 0.1
adult[adult['Age'] >= 40].shape() + np.random.laplace(loc=0, scale=sensitivity)
```