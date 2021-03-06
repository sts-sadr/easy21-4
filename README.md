## David Silver Easy21 Reinforcement Learning Monte-Carlo Assignment

Course Slides http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching.html

Sutton and Barto https://webdocs.cs.ualberta.ca/~sutton/book/ebook/the-book.html

Description:

1)	The player and dealer are each dealt 1 card

2)	The player hits or stands based on epsilon greedy exploration strategy

  *	Epsilon = 100 / (100 + N(s)) where N(s) is the number of times the state has been visited
  *	If epsilon is less than a random number from 0-1, then use the prior best action. If not, pick a random action. So as N(s) increases, epsilon decreases and you are more likely to follow the prior best action.

3)	If the player does not bust, the dealer draws until > 17

4)	At the end of each hand, the Q matrix is updated for each state / action combination as follows:

  * alpha = 1 / N(s, a) where N(s, a) is the number of times the state / action combination has been visited
  * hand reward = 1 win, -1 lose, 0 tie
  *	Q new = Q old + (alpha * (hand reward  - Q old))
  
Note that the Q values are updated for each state in the hand.

After 10 million hands:

![alt text](https://github.com/ezchx/easy21/blob/master/easy21_mc_graph_10m_greedy.png "10m runs")
