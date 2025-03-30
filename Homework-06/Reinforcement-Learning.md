## Real-world Markov Decision Process

One problem that could be formulated as an MDP is simply trading a stock -- buying or selling. One extremely simplified formulation of this problem is as follows:
- _State Space:_ $S=\lbrace P, \dot{P}, P500, \dot{P500}\rbrace$, where $P$ is the price of the stock in question, $\dot{P}$ is the instantaneous derivative of the stock price, and $P500$ and $\dot{P500}$ are the same metrics of the S\&P 500. This is of course a simplified version -- if this MDP were needed to make actual policy decisions, the state space would include many more variables.
- _Action Space:_ $A = \lbrace -M, -M+1, ..., M-1, M\rbrace$, where $-M$ corresponds to selling $M$ shares of the stock, and $M$ corresponds to buying $M$ shares of the stock. $M$ is a sort of hyperparameter denoting how much of a change you can possibly make at one step.
- _Transition Model:_ This would be purely based on the actual market value of the stock market at each step. If we had extensive historical data, this could be modeled as the probability of the price going down, staying the same, or going up, given the closest historical states to the current state.
- _Rewards:_ $R = \alpha(\Delta P)a$, where $\alpha$ is some hyperparameter, $\Delta P$ is the change in stock price after taking an action, and $a$ is the action taken. With this reward system, actions that either sell before the stock price goes down or buy before the stock price goes up are rewarded, while actions that sell before the stock price goes up or buy before the stock price goes down are penalized. Therefore, this reward model will maximize trading profit once optimized.


## RL in Healthcare
  
