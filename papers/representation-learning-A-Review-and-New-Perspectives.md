
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
We have proposed that a good representation is one that disentangles the underlying factors of variation.

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
1. **Expressive**: Good representations are expressive, meaning that a reasonably-sized learned representation can capture a huge number of possible input configurations. 
There's a simple counting argument to assess the expressiveness of a model pro-ducing a representation: how many parameters does it require compared to the number of input regions (or configurations) it can distinguish?
2. **Distributed representations**: where k out of N representation elements or feature values can be independently varied, e.g., they  are not mutually exclusive. Each concept is represented by having k features being turned on or active, while each feature is involved in representing many concepts.
In a distributed representation, an exponentially large number of possible subsets of features or hidden units can be activated in  response to a given input. In a single-layer model, each feature is typically associated with a preferred input direction, corresponding  to  a  hyperplane  in  input  space,  and  the code or  representation  associated  with  that input is precisely the pattern of activation (which features respond to the input, and  how  much). 
An example of non-distributed representation is the  one  learned  by most clustering algorithms, e.g., k-means, in which  the  representation  of  a given input vector is a one-hot code identifying which one of a small number of cluster centroids best represents the input.
3. **Sparse representations**: distributed representations where only a few of the elements can be varied at a time, i.e.,k < N.
4. **Non-parametric algorithms**: We understand non-parametric as including all learning  algorithms whose capacity can be increased appropriately as the amount of data and its complexity  demands  it,  e.g.  including  mixture  models  and  neural  networks where the number of parameters is a data-selected hyper-parameter.
5. **Advantages of deep architecture**: (1) deep architectures promote the re-use of features, and (2)  deep  architectures  can  potentially  lead  to  progressively more abstract features  at  higher  layers  of  representations (more removed from the data) because more abstract concepts can often  be  constructed  in  terms  of  less  abstract  ones.
6. **Probabilistic Graphic Models vs. Neural Networks**: Within the community of researchers interested in representa-tion learning, there has developed two broad parallel lines of inquiry: one rooted in probabilistic graphical models and one rooted  in  neural  networks.  Fundamentally,  the  difference  between these two paradigms is whether the layered architecture of a deep learning model is to be interpreted as describing a probabilistic  graphical  model  or  as  describing  a  computation graph.  In  short,  are  hidden  units  considered  latent  random variables or as computational nodes? 

The connection between these two paradigms becomes more tenuous  when  we  consider  deeper  models  where,  in  the  case of  a  probabilistic  model,  exact  inference  typically  becomes intractable.  In  the  case  of  deep  models,  the  computational graph diverges from the structure of the model.

7. **Principal Components Analysis** : PCA  learns  a  linear  transformation <a href="https://www.codecogs.com/eqnedit.php?latex=h=f\left&space;(&space;x&space;\right&space;)&space;=W^{T}x&plus;b" target="_blank"><img src="https://latex.codecogs.com/gif.latex?h=f\left&space;(&space;x&space;\right&space;)&space;=W^{T}x&plus;b" title="h=f\left ( x \right ) =W^{T}x+b" /></a> of  input <a href="https://www.codecogs.com/eqnedit.php?latex=x\in&space;R^{d_{x}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x\in&space;R^{d_{x}}" title="x\in R^{d_{x}}" /></a>,  where  the  columns  of <a href="https://www.codecogs.com/eqnedit.php?latex={d_{x}}\times&space;{d_{h}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{d_{x}}\times&space;{d_{h}}" title="{d_{x}}\times {d_{h}}" /></a> matrix *W* form  an  orthogonal  basis  for  the <a href="https://www.codecogs.com/eqnedit.php?latex={d_{h}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{d_{h}}" title="{d_{h}}" /></a> orthogonal directions of greatest variance in the training data.

The result is <a href="https://www.codecogs.com/eqnedit.php?latex={d_{h}}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?{d_{h}}" title="{d_{h}}" /></a> features   (the components of representation *h* )   that are  decorrelated. The three  interpretations  of  PCA  are  the following:  

a)  it  is  related  to probabilistic  models such  as  probabilistic  PCA,  factor  analysis  and  the  traditional multivariate Gaussian distribution (the leading eigenvectors of the  covariance  matrix  are  the  principal  components);  

b)  the representation it learns is essentially the same as that learned by a basic linear auto-encoder;

c) it can be viewed  as  a  simple  linear  form  of  linear manifold  learning,  i.e.,  characterizing  a  lower-dimensional  region in  input  space  near  which  the  data  density  is  peaked. 

PGA can be given a natural interpretation in factor analysis. 

8. **Probablistic Graphic Model**: We  can  express  as *p(x|h)* a probabilistic model over the joint space of the latent variables,*h*, and observed data or visible variables *x*. Feature values  are  conceived  as  the  result  of  an  inference  process  to determine  the  probability  distribution  of  the  latent  variables given the data, i.e. *p(h|x)*, often referred to as the posterior probability. Learning is conceived in term of estimating a set of model parameters that (locally) maximizes the regularized likelihood  of  the  training  data. 

**Directed latent factor models** separately parametrize the con-ditional  likelihood *p(x|h)* and  the prior *p(h)* to  construct the  joint  distribution, *p(x|h) = p(x|h)p(h)*

9.  **Explaining Away**, i.e., a priori independent causes of an event can become  non-independent  given  the  observation  of  the  event.
Latent  factor  models  can  generally  be  interpreted  as  latent cause models,  where  the *h* activations  cause  the  observed *x*. This renders the a priori independent *h* to be non-independent.

As  a  consequence,  recovering  the  posterior  distribution  of *h* , *p(h|x)* (which we use as a basis for feature representation), is   often   computationally   challenging   and   can   be   entirely intractable, especially whenh is discrete.

Example of **Explaining Away**: A  classic  example  that  illustrates  the  phenomenon  is  to imagine you are on vacation away from home and you receivea phone call from the security system company, telling you that the alarm has been activated. You begin worrying your home has  been  burglarized,  but  then  you  hear  on  the  radio  that  a minor earthquake has been reported in the area of your home. If you happen to know from prior experience that earthquakes sometimes  cause  your  home  alarm  system  to  activate,  then suddenly you relax, confident that your home has very likely not been burglarized.

The example illustrates how the *alarm activation* rendered two  otherwise  entirely  independent  causes, *burglarized* and *earthquake*,  to  become  dependent  –  in  this  case,  the  depen-dency  is  one  of  mutual  exclusivity.  Since  both burglarized andearthquake are  very  rare  events  and  both  can  cause alarm  activation,  the  observation  of  oneexplains  away the other.





## What are possible future research directions suggested in the paper? 
1. Research new priors and incorporate more priors into one algorithm. 
2. How to disentangle underlying explanatory factors
3. Combine methods  based  on  directly parametrizing a representation function and methods of the iterative type of computation (e.g. the inference  procedures  of  probabilistic  latent-variable  models)
4. Better understanding of optimization in deep neural netowrk, especially under unsupervised mode.

## What are the concepts that I need to look further into? 
1. Inference procedures of probabilistic latent-variable models
2. Restricted  Boltzmann  machine  (RBM)
3. 
