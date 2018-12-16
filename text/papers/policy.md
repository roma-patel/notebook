high level goal: determine how world knowledge affects ability to reason pragmatically. 

in current common-ground/knowledge representations the lexicon consists of a finite set of words. if this is a reference game, encode probabilities for words referring to objects.

assumptions in models of pragmatic word learning: 1. there is a single specific literal lexicon that everyone uses 2. everyone has access to and uses this lexicon 3. the current agent does not know it but this is what it wants to learn i.e., correct lexicon.

detail about model and paradoxes: literal listener that has a lexicon of word to object probability distribution vectors. to interpret a word, the listener reweights their prior expectation. so P_listener(object | word, lexicon) = c . lexicon(word, object) . P_prior(object)

Therefore a speaker should choose a word that soft-maximises the probability that listener will choose the correct target object. so P_speaker(word | object, lexicon) = c . exp(lambda(log(P_listener(object | word, lexicon) - cost(word))))

but then this is paradoxically a problem i.e., if P_listener exists, the speaker should soft-maximise the probability that the listener chooses the correct object, but given the speaker that chooses a word according to this policy, P_speaker should also implement a strategy that soft-maximises P_listener i.e., use Bayes rule to invert the decision. one option is to continue such iterations until a fixed point equilibrium. 

more problems: if agents switch roles, there is nothing that constrains them from using the same language i.e., optimizing task performance requires the speaker's lexicon to match the listener's lexicon, but there is no functional relation between the speaker and listener lexicons i.e., they never interact with each other. this is obviously not how typical human communication works i.e., we don't have distinct languages for participants or agents.

this paper explicitly says the above!

https://pdfs.semanticscholar.org/47f5/4d6425641550d0bcdab77175b3b2225304f5.pdf


dhruv batra paper: the game is grounded in a synthetic world of objects that have 3 attributes: color, style and shape and each has 4 possible values e.g., red green blue purple, dotted solid filled dashed, triangle square circle star. 
want to preserve the information asymmetry aspect. one agent is assigned a task G that consists of two attributes e.g., (color, style) and the other agent has to guess the pair of attributes e.g., (red, dotted) and they iteratively exchange utterances from finite vocabularies until the second agent guesses. both are rewarded based on accuracy of prediction.



w/ e!  

looking at world knowledge/common ground of interacting agents and how it relates to the ability to coordinate pragmatically. pragmatic models assume coordination with respect to a shared common ground, but humans' models of the world are never identical -- how much coordination can we expect when the speaker's model of the world differs from the listener's, how much can these models differ while still allowing people to make correct inferences, and what types of incorrect inferences arise? 





noah's first paper: 2 agents: either a base, literal listener and pragmatic speaker or pragmatic listener i.e., they are iteratively derived from one another (this is the iterative paradox). assumption is that there is one shared lexicon, but both agents have differing degrees of knowledge of it. they recursively learn and reason about the lexicon i.e., how it should be used (assign and update probabilities) to convey information about the referent. 

chris potts' paper: neural RSA agents: same concept, except embeddings that are randomly initialized and then learned through the process to represent words i.e., arguably less constrained than having a fixed lexicon, but what is really happening? and all communications are combined together? output of LSTM encoder is a gaussian distribution over referents (then softmax/classify to choose an object).

