# Swarm_robotics
Swarm robotics is an innovative approach to multi-robot systems which consist of a large number of simple and usually similar robots to collective achieve a common goal. This project was carried out by a team of three students where we demonstrated the typical and generic behaviour of swarm robots in the form of a pattern forming swarm. The simulation of the system was carried out using ROS and Gazebo as our simulation environment.
To allow for a simple simulation to demonstrate our project as a proof of concept we assumed the environment to be a static environment with only smooth surfaces. The simulation was carried out using the Pioneer 3-DX robot URDF specifications.


![image](https://user-images.githubusercontent.com/57947483/120608430-d392ec00-c46e-11eb-94d0-9d35a949b1e5.png)


 
				                Code for formation (above)
As seen in the above code we have come up with a simple control based on the distance of the robots from the master bot. This can be visualized as 3 concentric circles around the master bot and the slaves are allowed to take up and maintain a position anywhere on the circumference of the circle they are assigned to. In our demonstration the bot to the far-right acts as the master with the other robots taking up positions at a distance of 1m, 2m, 3m from the master respectively as seen in the code.


![image](https://user-images.githubusercontent.com/57947483/120609593-f376df80-c46f-11eb-8656-cd53f945f6ef.png) 
				                
                                 Initial position of bots (above)

      
 ![image](https://user-images.githubusercontent.com/57947483/120610013-61230b80-c470-11eb-999d-1f4f8f0d0c5d.png)

      
      
                                  final position of the bots (above)



![image](https://user-images.githubusercontent.com/57947483/120608709-1e146880-c46f-11eb-8153-8a21b56e78c9.png)
 
  
		                                      Obstacle avoidance (above)
To further demonstrate the capabilities of swarm behaviour and express the versatility and individuality of a robot as part of the swarm we decided to implement obstacle avoidance to our master bot. As mentioned above we have made use of the Pioneer 3-DX which comes with a pre-defined laser scan node that returns the distance of the obstacles in the vicinity of the robot in meters in the form of a python list.
To simplify our approach we only keep a track of the immediate obstacle in the robots path by using the values from the mid-point of our distance list and compare the sensor values on either side, the direction with least number of valid distance from our mid-point value is determined as the shortest distance and the robot is turned in the corresponding direction to avoid the obstacle. Once the obstacle has been avoided the values in the distance list are now infinite and hence, we can correct the course to return to the original robot path. In this approach the orientation of the robot at the end is changed due to drift and slippage. 
  			 
         
         
 ![image](https://user-images.githubusercontent.com/57947483/120614067-7732cb00-c474-11eb-8f59-10d6a8c4d45b.png)

 
 
		                                Initial position (above)			     
    
    
    
  ![image](https://user-images.githubusercontent.com/57947483/120614241-a47f7900-c474-11eb-9d53-1392112a607c.png)

    
    
                                  Clockwise turn to avoid obstacle (above)

  
  
  ![image](https://user-images.githubusercontent.com/57947483/120614398-d1339080-c474-11eb-8bba-f6f87885e6da.png)

  
  
                               Counter Clockwise turn to return to original position (above)  	    



![image](https://user-images.githubusercontent.com/57947483/120614538-f7593080-c474-11eb-9061-50ce88ce4174.png)



                                Final position of the swarm (above)

