bi-directional attention flow network is a multi-stage, hierarchical process that can represent context at different levels of granularity and uses bi-directional attention flow mechanism to create a context representation related to the query.

intro: neural attention is one of the key factors useful in these instances; being able to enable the system to focus on a targeted area/finer granularity within a larger context.

characteristics of attention mechanisms: 1. computed attention weights give you information about the most relevant information from context i.e., summarize context into a fixed size vector and look at weights. 2. they can be temporally dynamic i.e., at one time step, attention weights are a function of the previous time step. 3. they are usually uni-directional; the query attends on the context/input paragraph. 

model: 1. char embedding using CNN 2. word embedding is pertained 3. context embedding by taking in char+word for each word 4. attention flow layer: this couples query vectors and context vectors and produces feature vectors for each word that are query-aware and contextual 5. modeling layer: RNN to scan the context 6. output layer: provides answer to query

detail: 
char embedding layer maps each word to a high dimensional vector space using a CNN over training data. 1D inputs to the CNN are characters that are embedded into vectors and outputs of CNN are max-pooled over entire width to obtain a fixed size vector for each word. 
word embedding layer maps each word to a high dimensional space; using glove here. 
concatenation of char and word embeddings is passed to a two-layer highway network. this outputs two sequences of d-dimensional vectors i.e., a matrix with d rows and t columns for context and d rows and j columns for query i.e., incorporates both char and word.
contextual embedding layer is obtained by running an bilstm over char+word embeddings to model temporal interactions between words. output of both lstms is concatenated, therefore matrices are 2d rows and t columns and 2d rows and j columns for context and query respectively. 
attention flow layer serves the purpose of linking and fusing information from context and query that are now represented by previous matrices. attention is computed in two directions: context to query and query to context. First create a shared similarity matrix of t rows and j columns where cell(t, j) encodes similarity of context word t and query word j and this is computed by looking at similarity between the column vectors in the matrix before. this is done with a trainable scalar function that performs operations: concatenating h, t and hxt (element wise multiplication) and then multiplying by a trainable weight vector.
context to query attention! 

