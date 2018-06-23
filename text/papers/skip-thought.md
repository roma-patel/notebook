goal: unsupervised learning of sentence encoder i.e., want to train an encoder-decoder model that takes an encoded passage and tries to reconstruct surrounding sentences i.e., the context. 

problem: approaches for learning algorithms for composing words in sentence representations have always been task specific (these include recursive networks, recurrent networks, convolutional, recursive-convolutional) and all of these produce sentence representations that are passed to a supervised task, compared to the true label, and then backpropagated through the composition weights. these representations are then tuned for that specific task i.e., not general purpose. 

question: is there a task and a loss function that allows us to learn generic/general purpose sentence representations? here objective function?

input: sentence tuples
