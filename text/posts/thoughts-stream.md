first, the representation of the shape of an object is different from the representation of its use and purpose. second, vision alone can deliver an internal description of the shape of a viewed object (even when the object in question is not recognised in the conventional sense of it's most probable use and purpose). 

the hardest part is that humans are terribly good at vision; but is this because they are biased by prior knowledge? for example, if i know the purpose of a concept and have some indication of it, does this increase core visual capabilities? vision and language are therefore intrinsically connected, which begs the question: why are they disentangled and used as separate learning objectives instead of fusing in the same perceptual (read: latent) space?

so the primary job of vision is to derive a representation of shape (except vision or perception, in reality, should by no means be limited to only this; think about illumination, reflectances, textures and spatial geometry).. interestingly, this hints at primal sketches being important in that they make explicit, information about the two dimensional image and intensity changes.

however the derivation of shape information should require all three representational stages (how is this determined?), namely image, primal sketch, 2(1/2)-D sketch and 3D model representation i.e., a modular hierarchical representation. this is mostly what marr was trying to pitch, and essentially, allows representation of all visual aspects. 

---

bounded optimality and resource-rational bias. if you consider bounded optimality, you want to be able to determine what it is that allows agents (put another way: you want to design systems that allow agents) to perform well in instances that require them to plan on a horizon that goes beyond the planning horizon that they have. 

also consider the availability bias i.e., overestimating the probability of extreme events. it is not clear that is _not_ the right thing to do i.e., certain situations call for the bias. if you estimate the epected utility of an action (in the normal way; look at all possible outcomes, multiply utility by probability), here the space of all outcomes is too large, so usually generate a relatively small number of (weighted) samples and use this small sample of outcomes. note that now your cost increases linearly in the number of samples.

is biased or unbiased sampling better? in unbiased sampling, if the utilities are very different from probabilties i.e., the extreme event case we are interested in (extreme ~ high utility ~ low probability), this is an extreme skew in weight and there is a tradeoff between bias and variance. 

---

the current models (Noah Goodman's RSA and the lexical certainty or uncertainty models have very primitive notions of "world knowledge" representation i.e., in a reference game set setting, we have a set of words and a set of objects and for each word, a vector that represents the probability of the word referring to each object. 

what we want for the perspective project: distinct world representations for distinct agents. each agent reasons pragmatically about the same concept and chooses an output. want to visualize the spectrum of chosen outputs.

---

exact bayesian inference is intractable, except in the simplest models, and we therefore approximate bayesian inference. anything that requires approximation needs to determine an optimal tradeoff (here resources, time, performance). 

anchoring and adjustment; classic decision making, planning and psychological work that shows that bias increases with anchor extremity. tie this in with listener decisions when they start with a certain prior. if you have a very low prior over a referent to begin with, you are anchored in and adjustment from this point cannot happen (unless you have more world knowledge, parameters?). work also shows that increase in knowledge can abolish the bias, therefore help decision making. 

---

probabilistic inference in real time. this is esentially optimisation of the utility function, but now we incorporate decision time. the assumption is that the brain's inference process iteratively refines an approximation to the posterior distribution, where the first iteration starts from an initial distribution which is then approximated at each time step. we assume that agents update beliefs according to the Metropolis-Hastings algorithm, a transition matrix T allows temporal evolution of its belief distribution, where T is determined by the probability that a transition is proposed and the probability that this proposal is accepted. 

this is where anchoring and adjustment comes in; concretely, the psychological process underlying probabilistic inference is a series of temporal adjustments of the intial prior guess i.e., the anchor. iteratively, a potential adjustment is darwn froma  Gaussian distribution (with mean zero) and the proposed adjustment is either accepted or rejected. 

aside: Metropolis-Hastings: MCMC method to obtain a sequence of random samples from a distribution that we cannot directly sample from. this algorithm therefore proposes a way to construct a Markov chain that is ergodic and stationary (wrt the probability density pi defined on state space X i.e., if X(t) ~ pi(x) then X(t+1) ~ pi(x)) and this therefore converges in distribution to pi. 

---

one aspect -- want to be able to have one agent communicate with another. if agent1 takes in text, and decomposes it into it's "meaning representation" i.e., densely embedded vectors, vectors w multiple operations performed, lambda calculus expressions, can the second agent recover the text?
series of experiments -> first try logical forms/semantic parsing framework. let agent1 map the sentence to its functional units and dependencies. let agent2 take this representation and map it back. second try dense embeddings --> let agent1 perform (figure this part out more concretely) some compositional operations on word vectors of sentence. let agent2 take this in and try to map it back (or point out which of the test sentences is most likely). third is to to combine these --> one way is to simply perform both and objective is to minimize error. a more interesting way is to have a representation that actually combines both. think!

second aspect -- want to model different perspectives. e.g., consider a standard entailment dataset but different because we want to focus on the same concept represented in multiple ways (dataset would be one string/concept -> mapped to multiple perspective strings i.e., number of different ways it could be interpreted). consider n agents, each coming in with a different "knowledge set". let each agent construct it's meaning representation of the same string that incorporates his world knowledge. let each agent then predict which output string/concept entails his representation best i.e., based on that agent's reasoning/perspective.

for entailment, if two modules take in different text strings, embed them into representations, can we map the "common ground" i.e. knowledge we gain from both strings. this is two-fold; we can essentially be either mapping to a boolean or to another embedding representation (or text string or image.)

---

semantic networks are a different approach to having formal meaning representations i.e., instead of semantic parsing, but it's a very similar setup in the sense that you have entities or concepts that are related by functions or verbs to other concepts. e.g., child. what I want to do, is to use these semantic networks by constraining the amount of information that each agent gets and what we want is to see how this affects their ability to reason pragmatically or even co-ordinate with one another.

---

using language input to dynamically generate animated scenes; place objects in locations; visually represent structures etc. essentially want a means of direct visual output from natural language input i.e., this is more focused on generation and construction as opposed to classifying images or mapping to the correct image representation.

microsoft story maker lets users illustrate their stories on the fly, and then enter into a computer in natural language text strings. how this originated is kind of cool -- want to be able to create a platform that allows children to generate imagistic stories i.e., make it less cumbersome to search for the correct visual description or image based on the concept/storyline they have. useful as an education tool because it would provide someone with instant gratification about what they've written and how to visualize it. 

how it works: inputs in a sentence and decomposes it into relevant frames (semantic parsing etc., to find main elements and how they co-ordinate/act as functions to each other, but for this we're mostly interested in actor, action, background, object). from this kind of structured input, the graphics component then creates a representation of the scene based on the actor, object and background along with the action denoted by the actor and object in the corresponding background. 

---

use neural modules! don't want to reply on one monolithic structure, but have these flexible compositional structures that can be used to model the symbolic approaches to semantics and pragmatics. and these modules are learnt on the fly based on some signal they receive and what they currently want to optimse.

is it reasonable to think that a reasoning process should be split into several, distinct modules that perform their subtask and fire correctly in a task-dependent way and then have this all-encompassing structure that unifies them?

---



