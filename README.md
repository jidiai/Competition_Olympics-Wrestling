# Competition_Olympics-Wrestling

## Environment

<img src=https://jidi-images.oss-cn-beijing.aliyuncs.com/jidi/env74.gif width=600>


Check details in Jidi Competition [RLChina 智能体挑战赛 - 壬寅年秋赛季](http://www.jidiai.cn/compete_detail?compete=23)


### Olympics-Integrated
<b>Tags: </b>Partial Observation; Continuous Action Space; Continuous Observation Space

<b>Introduction: </b>Agents participate in the Olympic Games. In this series of competitions, two agents participate in the challenge arena sumo competition. The goal is to avoid falling off the challenge arena and try to knock each other off the challenge arena.

<b>Environment Rules:</b> 
1. This game has two sides and both sides control an elastic ball agent with the same mass and radius, which is located at both ends of a circular playing field.
2. At the beginning of the competition, agent of both sides can move freely within the circular field, but they can't touch the boundary of the field, otherwise they will be regarded as falling off the challenge arena and out of bounds.
3. Agents can collide with each other, but they will lose a certain speed according to the friction coefficient of the sphere. 
4. The agent has its own energy, and the energy consumed in each step is directly proportional to the applied driving force and displacement.
5. The energy of the agent recovers at a fixed rate at the same time. 
6. If the energy decays to zero, the agent will be tired, resulting in failure to apply force.
7. When one side falls into the challenge arena or the environment reaches the maximum number of steps of 500, the environment ends.


<b>Action Space: </b>Continuous, a matrix with shape 2*1, representing applied force and steering angle respectively.

<b>Observation: </b>A dictionary with keys 'obs' and 'controlled_player_index'. The value of 'obs' contains a 2D matrix with shape of 40x40 and other game-releated infomation. The 2D matrix records the view of agent along his current direction. Agent can see walls, marking lines, opponents and other game object within the vision area. The value of 'controlled_player_index' is the player id of the game.

<b>Reward: </b>Each team obtains a +100 reward when scoring the ball into the opponent's goal, otherwise 0 point.

<b>Environment ends condition: </b>The game ends when reaching maximum number of 500 steps or one side falls into the challenge arena.

<b>Registration: </b>Go to (http://www.jidiai.cn/compete_detail?compete=23).


---
## Dependency

>conda create -n olympics python=3.8.5

>conda activate olympics

>pip install -r requirements.txt

---

## Run a game

>python olympics_engine/main.py --map football

## How to test submission

You can locally test your submission. At Jidi platform, we evaluate your submission as same as *run_log.py*

For example,

>python run_log.py --my_ai "random" --opponent "random"

in which you are controlling agent 1 which is green.

---

## Ready to submit

Random policy --> *agents/random/submission.py*
