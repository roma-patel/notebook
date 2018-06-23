this proposes an adversarial evaluation scheme to determine if systems truly understand language. humans, for the large part, are undeterred by distractions (vaguely related to their ability to sift through information and extract the most important parts) and can answer a question, based on a paragraph, even in the presence of distractions in the form of similar (?) sentences. the method is to insert automatically generated sentences that are relevant to the target answer but do not change the output answer into paragraphs and test existing models. 

(if they are relying on something that is more clever than simple rule based heuristics and are actually modeling language, they should be similarly undeterred. but alas.)

method: use a simple set of rules to generate a sentence that does not answer the question but is/looks related. then fix grammatical errors via crowdsourcing. 

experiments: test on adversarial grammatical sentences. then test on adversarial non-grammatical sequences of English words. note the (significant) decrease in results.

models: bidaf and match-lstm. both deep learning architectures that predict a probability distribution over the correct answer.