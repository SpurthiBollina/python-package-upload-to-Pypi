
# prob_distributions_sb package 

Description: This program initiates Gaussian and Binomial 
		distributions, calculates mean, median and probability 
		density fuction for a given value. Plots histogram and pdf. 

# Files 

1. Generaldistribution is a parent class handles initiation and read a file 
2. Gaussiand and Binomial inherits general distribution and has additional functions 


# Installation 

pip install distributions-sb



Example code: 
```
from prob_distributions_sb import Gaussian, Binomial

gaussian_one = Gaussian(20, 3)
gaussian_two = Gaussian(30, 2)

print(gaussian_one + gaussian_two)

binomial_one = Binomial(prob = .5, size = 100)
print(binomial_one.pdf(7))
```
