(intuitively the RSA back and forth reasoning is similar to activation functions in a nn, but unlike activation functions the non-linear transformation applied here depends on the pragmatic context sets of the available utterances and referents.)

goal: different perspective on RSA i.e., learned RSA instead of standard RSA that requires a hand-built lexicon that is limited by. 

the Gricean view is that people are rational agents that share communicative goals, costs of production of utterances, expectation of utterances and current states of other agents i.e., belief states.

what I will refer to from now on as non-neural RSA:

learned RSA defines the model as a trained statistical classifier i.e., we want to infer the lexicon from the data. instead of making predictions according to a fixed calculation, we want to optimise the likelihood and make predictions based on examples it is trained on. so directly optimize the performance of the pragmatic speaker or pragmatic listener and this can be reformulated to start with either. i.e., begin with a literal listener, then have pragmatic speaker, pragmatic listener or the other way, depending on the task. 

feature representations: need a way to represent items in dataset and allow utterances to be formulated. let phi be a feature representation function that maps from a triple of (state, utterance, context) to a vector of real numbers. consider matrix of m attributes and n utterances, with counts or probabilities of utterances correlating with attributes in the dataset. can also allow more attribute features e.g., ones that intuitively involve negation. meaning if an attribute is unmentioned we want an indicator to specify this.

learned RSA is built on top of a log linear model. 

S_o(m | t, c; theta) xxx exp( theta^T phi(t, m, c)). here the lexicon is embedded in the parameters i.e., weights theta, and we want to train the model by searching for a theta to maximize the conditional likelihood that the model assigns to messages in the training examples. therefore, assuming training is done effectively, you're essentially increasing weights for correct pairings of utterances and attributes and decreasing for incorrect pairings. to find the optimal theta, want to maximize conditional likelihood of training examples using first-order optimization methods. we need the gradient of the likelihood wrt theta, and to simplify gradient derivation and improve numerical stability, maximize the log of the conditional likelihood. 

now define a pragmatic listener L1 based on S0 and pragmatic speaker S1 based on L1. the parameters for L1 and S1 are the parameters of S0, that are updated to maximize their own performance.
