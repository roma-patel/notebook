a dec-POMDP is an extension of a POMDP; and also a specific case of a POSG (partially observable stochastic game).  

so a dec-POMDP extends the 5-tuple of a POMDP; we now have  
_I_, the set of agents  
_S_, set of states
_Ai_, set of actions for agent i
_P_, state transition probabilties  
_R_, a global reward function where _R(s, a)_ are immediate rewards for actions from states  
_Omega i_, the set of obserfvcations for agent i
_O_, the observation probabilities  
_h_, horizon  


in general, we have a set of agents (> 1) that coordinate with one another to maximise a global reward based on local information. there is no Markovian signal during execution; the history of beliefs is stored, and policies map from histories to actions. a dec-POMDP extends a single agent POMDP by considering joint actions and observations.
