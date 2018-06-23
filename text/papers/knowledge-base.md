knowledge-base representations



A. Reporting Bias paper

1. failures of current methods.

a. it is often easier to have domain-specific KBs. this helps limit ambiguities
b. KBs can either be lexical KBs (contains linguistic information, syntactic patterns, special use of words) or ontological (contains world knowledge). you can also have episodic KBs i.e., only remembers certain instances of ontological KBs in a case-specific way, applicable to the current, limited context. 

b. application of knowledge: 
i. knowledge-based selection. use selectional constraints for WSD, resolving ambiguities.
problems: selecting an option based on constraints affects further selections at later timesteps. should be able to backtrack?
ii. knowledge-based inference. when there are no choices to choose from, apply knowledge to infer missing information. 

c. two types of systems that deal with "incompleteness" i.e., not having enough knowledge.
multi-engine systems (use a KB along with a statistical or syntax-based system and allow them all to examine the input) and human assisted systems (interact with humans to incrementally perform a task).




2. all-encompassing over-achieving aim

a. want to have a sense of "common-sense" world knowledge that humans share and rely on for pragmatic reasoning.

b. want to have a sense of "individual" world knowledge i.e., for different humans and agents that learn from different sources/amounts of information, does their knowledge component affect their reasoning ability? does it affect their ability to coordinate with other agents? what happens when agents have contradictory world knowledge components?



reporting bias:

the discrepancy between actual world reality and textual reality is referred to as reporting bias. this is evident by simple frequencies of occurrence, frequency of expected outcome, establish ground-truth common sense etc. 

important factors. 1. events and their frequency of occurrence are biased by how extreme the events are e.g., people are late more often than they are on time, people commit murder more often than they hug each other, or even breathe, eat etc. 2. important unmentioned properties. from millions of lines of text, we can gather that humans have eyes, ears and possibly more. but what about the less frequent terms like spleen, gall bladder, obscure intraventicular things will not show up in a statistically significant way? 3. some properties are more distinctive and descriptive than others even if more common and less important. e.g., it is most common to describe a person as having brown hair, fair skin, even if their most distinguishing factor is some other aspect.

aside: reporting bias can be just a consequence of Grice's maxim -- the conversational maxim of quantity that states that communication should be as informative as necessary,

final hypothesis:
1. the more the expected outcome, the less likely that people will communicate it. e.g., i paid for the book and then i owned the book. 
2  the more the importance of the expected outcome, the more people will report it.
3. the likelihood bias i.e., unusual things are reported more than common sense.
4. reporting bias varies by literary genre.
6. certain fundamental kinds of lexical and world knowledge don't get stated in text, may even be learned before language is acquired, so there may be no written transcript of it.






B. NELL paper

goal: instead of learning a single function or model from one data set, want to propose a never ending paradigm that reads the web 24 hours a day and has confidence weighted beliefs. NELL learns millions of features and parameters to read beliefs from the web and has learned to reason over the beliefs it reads and learns new beliefs i.e., it can synthesise new relational predicates.

related work: ml systems that persist over long periods of time can learn event structures. other work includes multi-task transfer learning, active and proactive learning and exploitation/exploration tradeoffs.

what is a never-ending learning problem? an ordered pair consisting of a set L = {L_i}, where the ith learning task L_i = {T_i, P_i, E_i} is  to improve the agent's performance, measured by the perf metric P_i on a perf task T_i, through experience E_i and some coupling constraints C - {{phi_k, V_k}}. Here phi_k is a real valued function over two or more learning tasks that specifies the degree of satisfaction of the constraint, and V_k is a vector in dices over learning tasks that specifies the arguments to phi_k.


C. ConceptNet paper

at a high level, earlier concept net versions collected facts and common sense knowledge, but concept net 5 collects sources of such facts and knowledge, representing them in a graph to allow traversal in a way that makes use of relations between concepts to further natural language understanding.

this is kind of cool, given that you traverse weighted links and can stop at each and mine information from the web (e.g., multiple urls) and traverse url links as well. 

elements: 
concepts i.e., words and phrases from natural language 
assertions i.e., the way that these concepts relate to each other
justifications i.e., sources or links to validate (or gain more information) about the associated assertions and concepts.

so especially for legal ambiguity, a child links to all other concepts and uses of the word child. 
