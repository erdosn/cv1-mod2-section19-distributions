
### Questions

### Objectives
YWBAT 
* Solve problems using poisson distributions
* Solve problems using geometric distributions
* Explain how the central limit theorem is applied to make claims on a population

### Outline


```python
import pandas as pd
import numpy as np

import matplotlib.pyplot as plt
```

### Poisson distribution problems
The Hulk smashes 17 items on average during a 6 minute time period.

a) Calculate the probability that Hulk smashes 10 items in 6 minutes.

b) Calculate the probability that Hulk smashes at least 1 item in 3 minutes.

c) During a ten minute period, what is the probability that 15 items are smashed?

----------------
<details>
    <summary>Solutions Here</summary>
    
    a) $$p = \frac{\lambda^x \times e^{-\lambda}}{x!} = \frac{\frac{17}{6}^x \times e^{-\frac{17}{6}}}{x!}$$
    
    Plug in 10 for x
       
       $$p = \frac{\frac{17}{6}^{10} \times e^{-\frac{17}{6}}}{10!}$$
       
       calculate 
       $$p = 0.033 = 3.3\%$$
            
     b) Start by converting lambda to match our time interval
    
        $$p = \frac{\frac{8.5}{3}^x \times e^{-\frac{8.5}{3}}}{x!}$$
        
    Plug in 1 for x
        
        $$p = \frac{\frac{17}{6}^1 \times e^{-\frac{17}{6}}}{1!}$$
    
    Calculate
    
        $$ p = 16.67\%$$
    
    c) Left as an exercise for the reader
    
</details>

### Binomial/Geometric distribution problems
Assume that 12% of the population pours their cereal on their milk. We choose 11 people at random.

a) What is the probability that the first person who pours milk on their cereal is the 4th person chosen?

b) What is the probability that the first person who pours milk on their cereal is the 4th or 5th person chosen?

c) There are exactly 5 people who pour their cereal on their milk in the group?

----------------------

<details>
    <summary>Solutions Here</summary>
    
    a) $$ p = 0.12^3 \times 0.88 = 0.0015 = .15\% $$
    
    b) $$ p = p(4) + p(5) = 0.12^3 \times 0.88 + 0.12^4 \times 0.88 = 0.0017 = 0.17\% $$
    
    c) $$ p = {11 \choose 8} 0.12^5 \times 0.88^6 = 0.0020 = 0.20\%$$
    
</details>

### What does the central limit state? 


```python
# Here's a population of 10,000 people between the ages of 10 and 60
population = np.random.randint(10, 60, 10000)

# this is the mean of the population
pop_mean = population.mean()
pop_mean
```


```python
# Let's do some sampling and see if we can get to the mean
samp_means = []
for i in range(50):
    sample = np.random.choice(population, size=30, replace=False)
    samp_means.append(sample.mean())
np.mean(samp_means)
```

### Assessment
