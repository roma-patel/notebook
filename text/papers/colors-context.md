goal: use RSA framework with neural speakers and listeners and introduce colour reference task. this (i.e., differentiating colour, pragmatically or otherwise) is an exceptionally interesting dataset even from a psychological perspective. 

data: first create colour representations (look into this more? some other paper does this in an interesting way, as well). log all the conversations (speaker-listener iterations), timestamps, targets and referents for each. other than that, this is the same learned RSA setup.

speaker: takes in the target plus context and generates a natural language utterance to distinguish target from context. the speaker is an LSTM that encodes the target contextually, based on the listener's beliefs (Gaussian distribution) and pragmatically generates the entire utterance. note that this is not incremental RSA.

listener: takes in utterance and context and generates Gaussian distribution to pick target from context. the base listener is not pragmatic, but further variants in iterations are i.e., they take speaker's beliefs into account. 

aside: i don't see this as being significantly different from andreas et. al., and the same problems exist. utterances are lost while sampling, priors bias decisions (but maybe this is a good thing?), only local context is considered (which is fine and maybe the entire point) and each conversation does not exist independently (which is not, for the different world/perspective scenario).
