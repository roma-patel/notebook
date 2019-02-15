abstract: given a language instruction ground to it's meaning representation (semantic parse) by learning from context i.e., cues in the environment and executing the instruction that the parse tells you to. 

(1) there exist key linguistic signals common in the environment and language used (2) can define a validation function that tests the state of the agent once it has interpreted and executed the instruction. (3) note that they have results that show "the final position of the agent provided enough supervision rather than intermediate points along the path" -- but this possibly says more about the kind of instructional data they are using (e.g., not non-Markovian temporal things, but things that specify the goal location). 

example setup of MacMahon: S is a set of positions on a map, a state is a tuple (x, y, o) for coordinates in a gridworld and orientation angle. they use maps with 141 states on average. actions are {left, right, move, null} and can change a state defined by T. 

important points:
(1) need a validation function. this looks at the meaning representation in logical form, looks at the executed trace (or sequence of actions) and validates that it satisfies constraints (detail: agent starts in (x, y, o) and visits points in the grid until the goal location, this allows us to create a function that checks if every constraint of the logical expression is satisfied).
(2) how does a semantic parsing expression map to action sequences?
