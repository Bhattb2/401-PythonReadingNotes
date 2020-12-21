# Random Numbers and Big O (Game of Greed 1)

## Generate Random Numbers

### How to use Random Module
- Python has a Random module that is helpful
- It includes functions such as:
- Randint
- Random
- Choice
- Shuffle
- Randrange

### Random docs
- Import Random
- random() --> is the key word. it generates random float number between 0.0 and 1.0.
- Random.randint(start,stop) --> Generates random numbers between start and stopcode.
- Random.random() --> generates numbers beween 0-1 and can be multiplied with 100 or 1000 to create higher numbers
- Random.choice([insert set here]): generates random selection from choices in the set
- random.seed(a=None, version=2) --> Initializes the random number generator
- random.randrange(start,stop[,step])
- random.shuffle(x[, random]) Shuffle the sequence x in place.
The optional argument random is a 0-argument function returning a random float in [0.0, 1.0); by default, this is the function random().
- random.sample(population, k) Return a k length list of unique elements chosen from the population sequence or set. Used for random sampling without replacement.
- random.triangular(low, high, mode) The mode argument defaults to the midpoint between the bounds, giving a symmetric distribution.

## What is Risk Analysis
- Use risk analysis to determine what to test
- Risk is introduced by many different types of changes
- The risk can be to many different things: Business, Testing, Premature Release, Software
- Pay attention to Effect, Cause, and Likelihood

## Why use Risk Analysis?
In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

## How to perform Risk Analysis?
There are three steps:

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified

## Big O Notation Video
- Sometimes, a pigeon carrying a USB drive will beat the internet data transfer
- The pigeon operation is Big O(1)
- It is always a constant travel time... how long does it take for the pigeon to fly?
- The data going across the network grows with the amount of data... so it has Big O(n)
- Spatial relationship to be similar to cutting grass
- The variable can be different than n
- Multiple variables can be used in the assessement
- They can add up
- Small terms are dropped
- Skimming/Bookmark Material for the Assignment

![References:]

(https://www.edureka.co/blog/risk-analysis-in-software-testing/)

(https://www.youtube.com/watch?v=v4cd1O4zkGw)

(https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)
