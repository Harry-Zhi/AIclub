## Reinforcement Learning


---------------------

#### MIT 6.S191 Lecture 6: Deep Reinforcement Learning
* [MIT 6.S191 Lecture 6: Deep Reinforcement Learning](https://www.youtube.com/watch?v=xWe58WGWmlk&index=4&list=PLkkuNyzb8LmxFutYuPA7B4oiMn6cjD6Rs)
  * RL: given data, choose action to maximize expected long-term reward
  * quantize interactions into episodes: s0,a0,r0, s1,a1,r1, ..., sT,aT,rT
  * key to RL: transition function *p(st+1,rt|st,at)*
  * objective in RL: finding policy $ \pi(s)=p(a|s) \$ to maximize reward
  * two major methods to find policy
    * policy learning: find *pi(s)* directly
    * value learning: given state and action estimate max future reward
  * *Q(st,at)* value: expected future reward at state *st* taking action *at* assuming subsequenct actions are going to be perfect
  * Bellman equation: relating one Q value to another Q value
  * max future reward for taking action *at* is the current reward plus the next step's max future reward 
  * How large is Q space? almost infinite
  * What is the loss in RL?
  * Approximate Q value with NN
  * Minimize distance between given Q value and max future reward
  * Q learning
   - initialize $\theta$
   - pick initial state *s=s0*
   - while loop
     - pick action *a* from some policy $\pi(s)$ and store reward *r* and new state *s*new
     - compute loss
     - update $\theata$
     - update old state theta
  * to pick action *a* from some policy $\pi(s)$ 
   - balance between explore and exploit
   - greedy exploration
   - most of the time pick the optimum action
   - with small probability pick a random action
   
  
    
#### Demystifying Deep Reinforcement Learning  
* [Demystifying Deep Reinforcement Learning](https://www.nervanasys.com/demystifying-deep-reinforcement-learning/)
* Breakout game using supervised NN
  - input image, output three actions
  - needs lots of examples, almost impossible
  - human only uses occasional feedback
* RL is in between supervised and unsupervised
* RL: sparse labels, rewards
* credid assignment probles: which action was responsible for reward
* explore-exploit dilemma: stick with one strategy or explore other strategies
* formalize RL: Markov Decision Process, set of states and actions
* policy: rules to perform actions, mapping from state to action
* one episode or game forms a finite sequence of states, actions and rewards
* Markov assumption: probability of next state depends only on current state si and action ai
* Discounted Future Reward: since environment is stochastic
* If environment is deterministic and the same actions always result in same rewards, then discount factor γ=1.
* Q learning: function Q(st,at) max future reward 
* the best possible score at the end taking certain action
* Q function: quality of action in given state
* Bellman equation: express Q value of state and action in terms of next state
* we can iteratively approximate the Q-function using the Bellman equation
* [proof of Q learning convergence](http://users.isr.ist.utl.pt/~mtjspaan/readingGroup/ProofQlearning.pdf)
* DQN: take game screens as input and output the Q-value for each possible action
* DQN optimize with squared error loss: prediction is current Q(s,a) and target is estimated max future reward
* Given a transition * s, a, r, s’ *
  - Do forward for current state *s* to get *Q* value for all actions
  - Do forward for next state *s'*  and calculate *max Q(s',a')*
  - set target Q-value to * r + γ max a’ Q(s’, a’) *
  - Update the weights using backpropagation
 * experience replay: store experiences, random mini-batch from experience replay are used instead of the most recent transition
 * Exploration-Exploitation: ε-greedy exploration
  

### Dissecting Reinforcement Learning
* [Dissecting Reinforcement Learning](https://mpatacchiola.github.io/blog/2016/12/09/dissecting-reinforcement-learning.html)
* Markov chain
  - set of states: S={s0,...,sm}
  - initial state: s0
  - transition model: T(s,s') 
* MDP: Markov chain including an agent and decision making process 
 - set of states
 - initial state
 - transition model
 - Set of actions: A={a0,a1,...,an}
 - reward function: R(s)
 - optimal policy: value iteration and policy iteration
 - model-free reinforcement learning: no transition model and no reward function
 
  
  
  


 



