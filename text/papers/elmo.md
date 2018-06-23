introduces word representations that are _deep_ and _contextualised_ by training with a language model objective and using the internal states as word representations. this improves sota on an (impressive!) array of tasks.


introductory: want to introduce a representation that can model the meaning of a word in terms of its syntax and semantics, but also its contextual use. use a bilstm trained with a coupled language model objective and interestingly create a representation using _all_ the internal layers i.e., learn a linear combination of vectors stacked above each word as input, for each end task. 

interesting (to me, for the sg project) aspects: variation in internal states of the LSTM they train. higher level states seem to capture contextual information, lower level states seem to model aspects of syntax. combining all seems to be a significant improvement (think of this as allowing the learned model that is a linear combination of them all to unfold and select (the types of semi-supervision) that are important to tune for the current end task. 

modeling details: innput in a sentence i.e., a sequence of tokens and consider a standard forward and backward lstm that is a language model. so we want the probabiltity of a sequence at a time step given the history. so first et a context indepedent representation (run a CNN/LSTM over characters) and run this through the forward lstm and at each step output a contextual representation. the topmost layer is used to predict the next token with a softmax layer. the backward then does the same in reverse i.e., predicting the previous token givne future context. their formulation jointly maximises ll of forward and backward directions.

once you have a representation for each bilstm layer, for inclusion in a downstream model, collapse all layers and you can either select one (top most?), or compute a map (task specific weighting) of all layers. but consider layer normalisation! each layer has a different distribution.

for task specific stuff, freeze weights of lstm and then concatenatethe elmo vector with the current word vector and use this enhanced input. can also add elmo at the output of the task rnn (introduce output specific linear weights). 

random details: in consideration of computational requirements (and to balance overall lm perplexity), halve all embedddings and hidden dimensions from the previous models.

different; about recasting.


