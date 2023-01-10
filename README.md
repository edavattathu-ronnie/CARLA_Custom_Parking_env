# CARLA_Custom_Parking_env
This is a repo to illustrate all the virtual environment developed using CARLA along with RoadRunner.

## First testing of Lightyear-0 vehicle:
As part of the thesis requirement, the training and the validation of the deep reinforcement learning framework needs to be executed on a Ligtear-0 vehicle, having the same set of geometrical constraints and vehicle dynamic definition. Since the parking manueveur was a low speed scenario, an extension for dedicatedly defining the dyamical behaviour of the vehicle was not used. Below a small snippet could be seen of the Lightyear vehicle moving in the virtual parking space.

https://user-images.githubusercontent.com/94734022/211490388-e091b2e8-890d-4ab3-a6ff-98ace0496626.mp4

## Virtual setup developed using CARLA and RoadRunner:
Lightyear didn't had any virtual setup to validate all their AI models or to test and benchmark their conventional planning and controller methodology. As part of this thesis, a virtual parking space, replicating Automotive Campus in Helmond was developed from scratch. Below an image of the parking space has been attached:

![Aerial_view_parking_lot](https://user-images.githubusercontent.com/94734022/211487890-c9ff7e1c-f366-4ab0-85c1-09c81fa2cce4.png)
![Zoomed_parking_space](https://user-images.githubusercontent.com/94734022/211487906-ffa73bab-25ae-4ce8-b228-871050df0ccc.png)

## Vehicle agent getting trained:
Since the placement of the parking sensor were not fixed, the initial sets of training was done using a Tesla Model3, which is illustrated in the video below. All the DRL algorithms of DDPG(Deep Deterministic Policy Gradient), TD3(Twin Delayed Deep Deterministic Policy Gradient), PPO(Proximal policy Optimization) and SAC+HER(Soft Actor Critic + Hindsight Experience Replay memory) was developed using Python using the framework of PyTorch. The vehicle agent trying to park below is demonstated using SAC+HER algorithm.

https://user-images.githubusercontent.com/94734022/211490526-ae3cbd89-24ed-4315-a2f4-e25307e9ab11.mp4

The simulation was ran in a asynchronous mode, with a fixed delta time-step. This was done to speed-up the training of the vehicle agent, since it can take weeks in real-time to train a vehicle to park appropriately. The only way to understand everything was working fine by using asynchronous mode, was by looking at the loss function and the reward return by the vehicle agent.
