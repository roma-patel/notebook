conversations, both research and otherwise, but paraphrased and distorted versions and therefore not entirely accurate depictions? but regardless, these are things that should not - for academic progress, especially - be forgotten. i also unintentionally forgot to tag each with a name, but I now somewhat appreciate having to match conversation to speaker, each time.
 
---

humans are remarkable -- the reason that humans, out of all class members have been able to acomplish so much is because they have the ability to incorporate information from multiple stimuli and fuse it together in a perceptual space that allows better reasoning. animals and birds and various lesser beings can take into account only select modes of information and stimulus factors. aside: but learning a language need not be reliant on words; animals coordinate with each other and _learn their language_ in a different, but still very tangible way.

interestingly however, for most of the key perceptual tasks that cognitive scientist and psychologists are interested in, the visual stimulus provides the largest insight; more so than words, sounds and actions. 

talking about the paper where models trained on images vs. text with different learning objectives have somewhat similar representations for same instances (but with arguably imprecise measures of similarity?). his students were considering doing somthing similar, using words and images in a shared space to measure erros and correct how a classifier learns and can learn better with additional modes of information. but consider an additional question: rather than trying to incorporate more or all modes of information, is there enougn information contained in an image to fully understand meaning? it makes sense to think that incorporating both sources (so image+text, as opposed to only image and only text) will help over either.

coordination failure is especially interesting from a mathematical point of view, when you want to formalise _why_ failure occurs between intercting agents. another area he's interested in is "the limits of rationality" and computational bounds of cognitive resources. sometimes the resources at hand are not enough to allow coordination. this can be as trivial as lacking knowledge representation, recursion that filters information out at each iterative step and what he is most interested in are _rationality bounds_. when you have computationally bounded agents, can they even achieve thier goals? this is mostly wrt perception, goal-pursuit and decision making, but he's written a bunch of papers that prove mathematically that there are situations where this cannot happen i.e., related to the computational complexity of selecting parameters and what you want to optimise. 


---


excited that people in NLP are starting to use RSA more; he's waiting for the day when it becomes this ubiquitous thing and people say things like "we added another "RSA layer" and this improves performance", the way people talk about current neural stuff, because that is really what it is; an added pragmatic layer.

character level pragmatics is obviously ridiculous and not how humans reason about things, but it's remarkable that it works so well. obviously overcomes the problem of sampling from all utterances (i suspect this is what helps the most?), but it's still strange to reason about characters and even do incremental RSA. 

another thing to look into regarding coordination and failure, is contrasting the knowledge and contrasting the objectives. this is relevant in social situations and in the realm of social niceties and politeness and implicature. conside a speaker who has a shift in his goal; he wants the listener to think of him in a certain way and now chooses utterances in that respect i.e., keeping the new objectives in mind. new information learned about the listener can also affect belief states and the goal each agent wants to optimise for. for politness, utterance costs are less important. you can have cheaper utterances, but the speaker will still want to choose one that is more polite; one that allows the listener to perceive him in that way that he wants. so now don't choose the utterance that is the most true, that allows the listener to perform his task in the best way, but choose the utterance that changes the listener's beleifs to make him appear the way that he wants? aside: this possibly violates all or most of Grice's maxims; does this mean we are not modeling rational agents any more? 

---

warrington's work suggests two things: first, the representation of the shape of an object is different from the representation of its use and purpose. second, vision alone can deliver an internal description of the shape of a viewed object (even when the object in question is not recognised in the conventional sense of it's most probable use and purpose). 

the hardest part is that humans are terribly good at vision; but is this because they are biased by prior knowledge? for example, if i know the purpose of a concept and have some indication of it, does this increase core visual capabilities? vision and language are therefore intrinsically connected, which begs the question: why are they disentangled and used as separate learning objectives instead of fusing in the same perceptual (read: latent) space?

so the primary job of vision is to derive a representation of shape (except vision or perception, in reality, should by no means be limited to only this; think about illumination, reflectances, textures and spatial geometry).. interestingly, this hints at primal sketches being important in that they make explicit, information about the two dimensional image and intensity changes.

however the derivation of shape information should require all three representational stages (how is this determined?), namely image, primal sketch, 2(1/2)-D sketch and 3D model representation i.e., a modular hierarchical representation. this is mostly what marr was trying to pitch, and essentially, allows representation of all visual aspects. 

---

when you have an interactive setting with agents that are required to coordinate with each other, yes, there is a lexicon and shared common space that we want to approximate. but when you conflate everything into one feature space, can you disentangle this and tear apart the language model and the world model and update belief states in the way that you want? 

---


there is a definite tradeoff between having rich user driven annotations or corpora , as opposed to something that is model oriented and task driven and designed to only let your system learn this one, specific, fine-grained aspect of the world i.e., syntactic structure or predicting a word or describing a scene amongts the multitude of tasks that we can train a system to perform. but are richer and more complex annotations a good thing? at what point do you think we can filter out things that aren't necessary even to humans for our internal learning mechanism? in a learning environment (e.g., simulated world that has objects with real attributes, spatial geometric aspects) can we learn to filter out what isn't immediately necessary to an agent that wants to optimise for a task (e.g., navigation)? so yes, there are things that aren't necessary to an agent in a world, but you can model agents to still perform intelligently. thinking about local context that should be given more importance; humans can reason and filter out noise remarkably well, even in the midst of chaos, to focus on what is important. we should be able to model intelligent beings that attend to what is immediately important to the task at hand, while being aware of an taking into account all factors e.g., local vs. global factors.


---

bounded optimality and resource-rational bias. if you consider bounded optimality, you want to be able to determine what it is that allows agents (put another way: you want to design systems that allow agents) to perform well in instances that require them to plan on a horizon that goes beyond the planning horizon that they have. 

also consider the availability bias i.e., overestimating the probability of extreme events. it is not clear that is _not_ the right thing to do i.e., certain situations call for the bias. if you estimate the epected utility of an action (in the normal way; look at all possible outcomes, multiply utility by probability), here the space of all outcomes is too large, so usually generate a relatively small number of (weighted) samples and use this small sample of outcomes. note that now your cost increases linearly in the number of samples.

is biased or unbiased sampling better? in unbiased sampling, if the utilities are very different from probabilties i.e., the extreme event case we are interested in (extreme ~ high utility ~ low probability), this is an extreme skew in weight and there is a tradeoff between bias and variance. 

---


humans are able to move up and down this abstraction hierarchy fairly easily, what will it take for machines to do so? we need a model of everything the robot can do i.e., map word meanings to instances of the world; but this is hardly only about command and instruction understanding and isolation/mapping. dialog and interactions are recursive, social processes; and most importantly they are governed by uncertainty. so if you have observations coming in and you have a world model (map language to aspects of your current world), you want to infer actions that a robot can and should take. so observe langauge, estimate the mental state of the human, and perform actions i.e., try to interpret natural language commands by apping to fixed physical world states. a second direction is to infer things that a robot can say to a human -- want to be able to change the mental state of a human and resolve ambiguities.

---

everytime i read about the RSA stuff in simulated worlds; relate it to what we work on with novels, texts and real-life story-scenarios and note the difference i.e., it would be interesting to see how models of speakers and listeners can be set in a real-world scenario. what would be interesting is if you consider a social media application; you have tweets from users, each a distinct "agent", can you model how they coordinate or fail to coordinate? except failure in this case isn't actually well-defined when they're not operating in a goal-oriented way.

what does it mean to be a character? in a first-person retelling, a narrator could be never referred to in a story, but is an intrinsic part of the plot and development. he is still a _character_, just not as physical a presence as other characters that he refers to in his retelling i.e., characters that have names, identities, locations, corefer to other things and so on. but note that these coexist with the metaphysical narrator character, so how can you disentangle these? interestingly, he wrote about this briefly in a paper and there was no obvious solution, if there even can/should be, and it's been left for later work. 

what is interesting is coreference in a larger sense; especially in stories with convoluted plots that require you to backtrack, consult previous temporal events or require you to trace back in time. but even when you consider a simple, forward-only scenario; can event/location coreference for a novel be modeled? e.g., as humans, we can determine a shift in the story even when it isn't explicitly marked (note: mildy amusing that sometimes humans _can't_ do this; he said that it's actually really hard getting accurate annotations, because this is a hard task to begin with). what's also interesting is how the granularity changes and you don't always consistently have a unit word, sentence, or paragraph, even. 

write more about: modeling characters, plot flow, event flow, scene shifts (also questions about the vision/perceptual/coordination stuff that he had interesting insights on)

---



