This is an analytical (mathematical) approach to fit and model a probabilistic Markov Model and perform sentiment analysis
to text data coming from an airline passangers.

Markov Property:

Aij = p (s(t)=j | s(t-1)=i)

We basically have 3 Markov Classifiers all trained with the 3 sentiment classes (positive, neutral, negative). 
The model uses add-one smoothing method to fake count the i->j step transition.
The probabilities are converted to log probabilities in order to avoid small multiplications. 

The fitting process is made by initializing the p (initial matrix ~ no prior state | 1D matrix with the vocabulary lenght as size) 
and A (state transition matrix | 2D matrix ~ vocabulary length x vocabulary length) that is populated by transition counts.
Finally the log likelihood is computed for each class and the highest possibility as a number is chosen as the prediction result. 

<img src="https://latex.codecogs.com/png.image?\dpi{110}&space;P(s_{1}...T)&space;=&space;p(s_{1})&space;\prod_{T}^{t=2}p(s_{t}&space;|&space;s_{t-1})" title="P(s_{1}...T) = p(s_{1}) \prod_{T}^{t=2}p(s_{t} | s_{t-1})" />


The accuracy score of the test set is way lower than the train test, but the point of this project was to build a Markov Model from scratch rather than
produce a robust sentiment analysis model.

More about Markov Models: 
https://www.skyradar.com/blog/artificial-intelligence-hidden-markov-model-classifiers-and-radar-objects-classification-by-machine-learning-2-2

