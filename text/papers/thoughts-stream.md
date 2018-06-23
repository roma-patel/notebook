the current models (Noah Goodman's RSA and the lexical certainty or uncertainty models have very primitive notions of "world knowledge" representation i.e., in a reference game set setting, we have a set of words and a set of objects and for each word, a vector that represents the probability of the word referring to each object. 

what we want for the perspective project: distinct world representations for distinct agents. each agent reasons pragmatically about the same concept and chooses an output. want to visualize the spectrum of chosen outputs.

---

method 1: can we train agents with different knowledge sets as "world knowledge representation" and see how they reason pragmatically? i.e., consider the U. S. Code setup and let agent1 have knowledge about "presidents", agent2 about "public health", "transportation", "crime" etc., and then each agent reasons about the same concept or word. how does this affect their pragmatic coordination and reasoning capabilities?
pitfall: this can be seen as merely an evaluation of representations?
enhancement: also incorporate the "general" knowledge set, plus some extra architectural stuff that allows them to reason i.e., they are not reliant on only their knowledge vectors.


method2: try incorporating the original approach in a reference game setting?

---

one aspect -- want to be able to have one agent communicate with another. if agent1 takes in text, and decomposes it into it's "meaning representation" i.e., densely embedded vectors, vectors w multiple operations performed, lambda calculus expressions, can the second agent recover the text?
series of experiments -> first try logical forms/semantic parsing framework. let agent1 map the sentence to its functional units and dependencies. let agent2 take this representation and map it back. second try dense embeddings --> let agent1 perform (figure this part out more concretely) some compositional operations on word vectors of sentence. let agent2 take this in and try to map it back (or point out which of the test sentences is most likely). third is to to combine these --> one way is to simply perform both and objective is to minimize error. a more interesting way is to have a representation that actually combines both. think!

second aspect -- want to model different perspectives. e.g., consider a standard entailment dataset but different because we want to focus on the same concept represented in multiple ways (dataset would be one string/concept -> mapped to multiple perspective strings i.e., number of different ways it could be interpreted). consider n agents, each coming in with a different "knowledge set". let each agent construct it's meaning representation of the same string that incorporates his world knowledge. let each agent then predict which output string/concept entails his representation best i.e., based on that agent's reasoning/perspective.

for entailment, if two modules take in different text strings, embed them into representations, can we map the "common ground" i.e. knowledge we gain from both strings. this is two-fold; we can essentially be either mapping to a boolean or to another embedding representation (or text string or image.)

---

semantic networks are a different approach to having formal meaning representations i.e., instead of semantic parsing, but it's a very similar setup in the sense that you have entities or concepts that are related by functions or verbs to other concepts. e.g., child. what I want to do, is to use these semantic networks by constraining the amount of information that each agent gets and what we want is to see how this affects their ability to reason pragmatically or even co-ordinate with one another.

---

mark + john

that there are 2 agents with this kind of informational asymmetry based on the information that they have i.e., we can't function with only one of the agents; and our goal is to reason pragmatically about the input and map it to some output. and obviously a fundamental aspect of this is the knowledge that each agent has; so how their vocabulary is constrained and like the probabilities for referring to objects.

one super interesting outcome of this is the idea of mapping perspectives; so now that we have these agents set up, each with a distinct world knowledge component; and for this experiment we want to constrain each knowledge component to keep them different from one another. and if we set up these n agents, each with different knowledge sets and let them reason about the same input( so a concept or even a news article) we want them to reason about what they've read based on context in their world and then map to some output. this is interesting because at the end you have this perspective map that allows us to see how for humans, having different knowledge sets, affects their outlook or perspective on the same concept. 


informational asymmetry: one agent has information about the first word/text structure i.e., embedding, position in semantic network and has information about the semantic concept/correspondence e.g., entailment or contradiction. the second agent has information about the second word/text structure.

---

ellie!

thinking about incorporating world knowledge into an "agent", there are two different things you want to consider - will this representation optimise the task at hand or will it generally be interpretable and encode actual common-sense information. so what people do now is the first aspect; looking into the different ways in which people incorporate the common ground/world knowledge, shows that they are extremely primitive lexicons or mappings from words to objects that encode probabilities. and you can either learn the lexicons through iterations of the game, or keep it static (which means it's entirely statistical and dependent on the examples you got the probabilities over). for the latter, it would be ideal if we could use a semantic network (explain) that relates concepts with functional properties (closed class) that allow 1. reasoning about meaning and 2. linking to similar concepts by traversing the graph and also links to other resources.

---

james (also jeff?): 
using language input to dynamically generate animated scenes; place objects in locations; visually represent structures etc. essentially want a means of direct visual output from natural language input i.e., this is more focused on generation and construction as opposed to classifying images or mapping to the correct image representation.

microsoft has this interesting approach called story maker, where they let users illustrate their stories on the fly, and then enter into a computer in natural language text strings. how this originated is kind of cool -- want to be able to create a platform to allows children to generate imagistic stories i.e., make it less cumbersome to search for the correct visual description or image based on the concept/storyline they have. useful as an education tool because it would provide someone with instant gratification about what they've written and how to visualize it. 

how it works: inputs in a sentence and decomposes it into relevant frames (semantic parsing etc., to find main elements and how they co-ordinate/act as functions to each other, but for this we're mostly interested in actor, action, background, object). from this kind of structured input, the graphics component then creates a representation of the scene based on the actor, object and background along with the action denoted by the actor and object in the corresponding background. 

obviously need to deal with linguistic/general NLP issues regarding the story e.g., coreference or anaphora resolution, negation, entailment, ellipsis. 

another area of interest is trying to incorporate various linguistic aspects into graphics: so for example, if a person says, move this under the table or over it, we need to understand and represent these semantics of spatial expressions. 

---

daniel: 

use neural modules! don't want to reply on one monolithic structure, but have these flexible compositional structures that can be used to model the symbolic approaches to semantics and pragmatics. and these modules are learnt on the fly based on some signal they receive and what they currently want to optimse.

is it reasonable to think that a reasoning process should be split into several, distinct modules that perform their subtask and fire correctly in a task-dependent way and then have this all-encompassing structure that unifies them?

 
