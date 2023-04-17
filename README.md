# FootStepModel_with_RL

<p align="center">
  <img src="./Demo/footstep.gif" />
</p>

## When open it, if show normalmap settings warning, please click ignore.

## We implemented footstep model with rl to creating realistic footsteps.

Pengxiang Jia, Yide Ma

This is a novel implementation of paper: [Footstep navigation for dynamic crowds](https://people.cs.rutgers.edu/~mk1353/pdfs/footstep-navigation.pdf).
We have utilize different rl algorithm to train the footstep model.

# Environments: 
!conda create -n xxx python=3.9
!conda activate xxx
!pip install mlagent==0.30.0
#also install cuda and pytorch in your environments
#i used cuda 11.6 and pytorch 1.12.1
#unity version we use: 2019.4.29f1
#ml-agent version in unity editor i used is 2.0

# Running
The pretrained model is already set to each agent. 

# Training
if you want to play around with training, use the command below:
!mlagents-learn C:\Users\xxx\OneDrive\Desktop\FootStepModel_with_RL\Config\MyBehavior.yaml --run-id=MyBehavior --force

if you want to resume training from a mlagent check point in the result folder
!mlagents-learn C:\Users\xxx\OneDrive\Desktop\FootStepModel_with_RL\Config\MyBehavior.yaml --run-id=MyBehavior --resume


before rl-algorithms training:

![image](./Demo/old.gif)

after ppo training:

![image](./Demo/result.gif)


the training curve:

![image](./Demo/loss.png)

# Viewing the results
#if you want to visual, the mlagent training folder contains .pt and .onxx is in the demo folder, with name "MyBehavior".
!tensorboard --logdir results --port 6006
#then open http://localhost:6006/

# Running naive A* algorithm
if you want to run naive A* algorithm we implemented,  there is a file "AStar.zip/A_star.unitypackage" under Demo folder. Open a new unity project and import it. Import all things. Open assets/AStarWrapper/Scenes, then play. you can left click for representing the agent and right click for the goal. it will produce the path by A* algorithm. 

![image](./Demo/A_star.png)

To be continued...



