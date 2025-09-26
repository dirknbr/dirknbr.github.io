# Inferring the joint probability of 3 events from joint pair probabilities

Imagine you have 3 binary events (x1, x2, x3) and you want to find the joint probability p(x1, x2, x3), but you only know p(x1, x2), p(x1, x3) and p(x2, x3). 
All p() sum to 1. We know that if we sum over one variable we get the pair joint from the triple joint. 

This can be useful if we know pairs of two attributes but there is no cross tab between 3 variables. 

So we have 2**3 = 8 unknowns (or 7 if we factor in the sum constraint) and 3 * 4 knowns, however, there is redundancy so we actually have less than 7 knowns. 
So this means there is no unique solution. Typically this can be solved with a max entropy approach. In this example we compare the max ent approach to 2 competing approaches. 

- Brute force: we generate lots of possible normalised p(x1, x2, x3) cases using Beta distribution and then find the one that has the smallest squared error with the 3 known joint probabilities. 
- We generate N samples from p(x1, x2) and p(x2, x3) and implied conditional probabilities. We then aggregate the sample to estimate p(x1, x2, x3). This assumes a chain x1 -> x2 -> x3. 

In the max ent approach we also impose an inequality constraint that the error between the implied and actual double joints is below a threshold.

Using 200 synthetic examples of known double and triple joint probabilities, we test whether any of the 3 methods performs best in terms of a small error between true and estimated triple joint. 

We find that the max ent approach does best, brute force does worst. We also checked whether an averaged blend of the three could do better, it doesn’t. So this shows that max ent is pretty robust. 

```
           maxent          bf         sim       blend
count  200.000000  200.000000  200.000000  200.000000
mean     0.014970    0.024962    0.019601    0.015578
std      0.008622    0.017489    0.009930    0.009223
min      0.004477    0.006336    0.002137    0.002692
25%      0.007793    0.012597    0.011709    0.009132
50%      0.012393    0.017957    0.018866    0.013213
75%      0.019964    0.033672    0.026529    0.019691
max      0.045763    0.116291    0.051152    0.061373
``` 
