spatial language understanding has so far been explored in 2D realms and entirely from language; next big advances require real-world interactive datasets, where a bot can experience everything that a human would, interact with them, and learn to survive in the environment and understand the happenings occurring around it -- for the first time, it has access to nearly all modes of informaiton that a human would, as opposed to only text and images. 

will create richer data that requires scene understanding, will be in first person perspective, will be at a much larger scale (e.g., Google Maps data around the world), will have more natural language.

---

speaker-follower paper  

use an RSA-like speaker-listener setup, where a speaker model generates new, pragmatic utterances such that these allow a listener model to generate routes (action sequences) to reach the correct intended position. 
  
the speaker encodes a sequence of visual observations at each timestep plus actions taken in the route using an LSTM and outputs a description _d_ i.e., a sequence of words. the listener encodes the sequence of words in the route description using an LSTM and outputs a route _r_ i.e., a sequence of actions. more detailon each below, but these are then combined into an RSA-like speaker-follower system where the speaker is used at both training and test time to generate descriptions for the route that the listener is supposed to follow. at test time, when the follower has only text instruction _d_ to follow, it first predicts a set of possible _r_ samples, the speaker pragmatically ranks these i.e., chooses the route that best provides explanation of _d_ in context. 

we now have base speakers (PS) and followers (PF); where PS takes in a target route + context and generates _d_ and PF takes in a description _d_ and generates a route. given an instruction, we can take the top _k_ generated routes from PF and for each route (that has a p1=P(r|d) from PF), give it to PS and obtain p2=P(d|r). The score for this route is then p1^x * p2^(1-x), where x is a hyperparam tuned to maximise accuracy of follower.


----

what we have:

language-module can take in description _d_ and predict a goal state. env-module can take in current goal state and predict true goal state. pragmatic follower combines distributions from both.

our language-module is not a speaker, but if you think of a base agent as a black box that can give you a P(d|r) (speaker) or P(r|d) (listener), 

the reason the speaker is _pragmatic_ is that it gives you a P(d) in context, as opposed to wrt. every possible element.

-

PF can take in description _d_ and predict a goal state. PS can take in the true goal state and generate description _d_. 
 

