
# Representation Learning: A Review and New Perspectives
Yoshua Bengioy, Aaron Courville, and Pascal Vincent

## Paper Type: 
Review

## Paper Topic
Feature Engineering or Data Representation

## Paper Summary
This paper reviews the work in unsupervised feature learning and deep learning, covering advances in probabilistic models, auto-encoders, manifold learning and deep networks.
The authors tried to answer: 
1. What makes a better representation than another?
2. How to do feature extraction?
3. What are good objectives for learning good representations? 

## What are the problems? 
Current maching learning algorithms are unable to extract or organize discriminative information from the data (i.e. data representation). The process of feature engineering depends too much on human ingenuity and prior knowledge.

## Why it's important to solve the problems? 
The performance of many maching learning algorithms depend heavily on the choice of data representation (or features) on which they are applied. However, current process of deploying machine learning algorithm puts lots of efforts into feature engineering. To expand the scope and ease of machine learning applicability, we want to have less dependency on feature engineering. So that novel applications could be constructed faster and move towards artificial intelligence. 

## What solutions are the authors proposing? 


## How do the authors solve the problem? 
The paper covers three major approaches for feature engineering: 
1. The probabilistic models (both the directed kind such as sparse coding and the undirected kind such as Boltzmann machines)
2. The reconstruction-based algorithms related to auto-encoders
3. The geometrically motivated manifold-learning approaches.

It also Reviews:
1. Practical concerns and guidelines for deep learning: It's more like an art to tune a deep neural network.
2. Incorporating generic AI-level priors
3. Inference
4. Optimization

## What are the important concepts and technologies that are explained well in the paper?


## What are possible future research directions suggested in the paper? 
1. Research new priors and incorporate more priors into one algorithm. 
2. How to disentangle underlying explanatory factors
3. Combine methods  based  on  directly parametrizing a representation function and methods of the iterative type of computation (e.g. the inference  procedures  of  probabilistic  latent-variable  models)
4. Better understanding of optimization in deep neural netowrk, especially under unsupervised mode.

## What are the concepts that I need to look further into? 
1. Inference procedures of probabilistic latent-variable models
2. 
