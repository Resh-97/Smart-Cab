# Smart-Cab
Uses RL techniques and NLP concepts

### Problem Statement: 
A self-driving cab company Smartcab wanted to design a simulation of a self-driving cab.Demonstrate the use of **RL techniques** to develop an efficient and safe approach for tackling the issue. 
 
### Project Description:  
The Smart-cab's job is to pick up the passenger at one location and drop them off in another. It takes care of: 
  * Drop off the passenger to the right location.  
  * Save passenger's time by taking minimum time possible to drop off 
  * Take care of passenger's safety and traffic rules  

Aspects that are considered while modeling an RL solution to this problem: rewards, states, and actions.  
 
Company allows users to book a cab by sending a free text SMS containing source, destination and time of travel. Since SMS is a free text, different users can send the same message in different ways.  
 
For example: 
  1. I want to book a cab from cyber city to sector 48 at 5 pm.  
  2. Please book my cab with pick up from cyber city, destination sector 48, and time of pickup 5 pm.  
  3. Book a cab for me from sector 48, my pick-up is from cyber city at 5 pm.  
 
So, the challenge for the company is to parse this free text and fetch three entities:  
  * Pick up location  
  * Destination  
  * Time to pick up 
 
### Project:

  #### Environment:
  ![Output 1](/images/output1.PNG)

 There are  six possible actions: 
   1. south 
   2. north 
   3. east
   4. west 
   5. pickup 
   6. dropoff 
 This is the action space: the set of all the actions that our agent can take in a given state. 
 
 #### Q-Learning Process:  
   * Initialize the Q-table by all zeros. 
   * Start exploring actions.
   * For each state, select any one among all possible actions for the current state (S). 
   * Travel to the next state (S') as a result of that action (a). 
   * For all possible actions from the state (S') select the one with the highest Q-value. 
   * Update Q-table values using the equation. 
   * Set the next state as the current state. 
   * If goal state is reached, then end and repeat the process. 
 
Q-table was established over 100,000 episodes. Following are the values obtained after training.  

 ![Output 2](/images/output2.PNG)
 
 #### Evaluation the Agent: 
 
 ![Output 3](/images/output3.PNG)
 ### INFERENCE: 
 We can see from the evaluation, the agent's performance improved significantly and it incurred highly reduced penalties, which means it performed significantly well in pickup/dropoff actions with 1000 different passengers. 
