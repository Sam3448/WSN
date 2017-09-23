# WSN
Code written by Weicheng Zhang. 

## Introduction
This project aims to develop a effective Intrusion Detection System(IDS) to detect attacks towards Wireless Sensor Network. In this project, I implemented a two-layer network protocol to detect abnormal Wireless Sensor Nodes by monitoring their power levels and get rid of it if necessary. WSN are widely used in geology study and health care systems that are built inside human bodies, which makes this work important.

## Instruction & Parameters
To run the whole program, simply run /com/networkBuild/Runnet.java, and follow the instruction to input all parameters needed in the program.

1. Overview
 	This code is for paper "Using network traffic to infer compromised neighbors in wireless sensor nodes". This includes lower level and upper level according to the protocol. This network can be attacked, and it will also detect the compromised node and remove it from the route.

2. Introduction to the code
	* Runnet is the main function of the project. In the NetFormation class, source and destination indicates the source and the destination of the network. All parameters in this project is identical to those in the original matlab code. 
  	* LowerLevel is used to form and reform the network. Node defines attributes of each node, which includes the coordinates of each node and distance to other nodes.
  	* UpperLevel is used to monitor the route and changes the route when one node of in the route is compromised. Whether a node is compromised or not is decided by its transmitting speed, which is monitored by its child node. AdjustPsend is a class to show the energy status of a node according to the dynamic duty cycling table.
  	* Attack is the class for attacking strategy. This part contains three kinds of attacks, 1: physical damage, 2: jamming, 3: man-in-the-middle. 

3. To run the code
  	As Runnet is the main function, user can run this code by either using IDE or using instructions. To run WSN_Detection.jar, user can use instruction: java -jar PATH/WSN_Detection.jar source destination attack.   

  	For example, first run java -jar ./WSN_Detection.jar, and there will be several input that needed to be completed to run the code. These basic parameters are: number of nodes, source node, destination node, attack or not, which kind of attack method to choose, and the round the attacker want to set the attack. After setting all these parameters, the code will come to network transmission part, and start running.

### Example:
`$ java -jar WSN_Detection.jar`  

--------------------PARAMETER SETTIN--------------------   
Please input the number of nodes : 10
Please input the source node (1-10) : 2

Please input the destination node (1-10) : 4

Please input whether to attack (true/false) : true

If attack, please input attack method(1-4)

1: Physical Damage  
2: Jamming  
3: Man-in-the-middle  
4: Semi-damaged  
Please select the attack method : 3  
DEPLOY : AttackMethod 3  => Man In The Middle  

Please input the round to attack (start from 1): 2   

--------------------TRANSMISSION START--------------------  
Hop times(Number of routers) : 2  

Source to Destination :   2 3 8 4   
	Round = 7  
	Node 3 compromised, Trying to find another route  
 
Hop times : 1  
Source to Destination :  2 8 4   
	Round = 133  
	Node 8 dead naturally, Looptime = 133  
