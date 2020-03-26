# Package Description: 

This package is a glorified global planner which generates the most efficient path in terms of producing GPS waypoints from start to finish. It has an added ability of introducing blacklisted areas. Blacklisted areas are those regions which the user is sure or atleast certain, that there exists an obstruction at the said place. Recommended viewing would be that of a mapviz search panning the predetermined area first. 

## Tutorial:

Copy the mapviz config file for this package into your home directory. For mapviz setup refer [here](https://github.com/leander-dsouza/Gazebo/blob/master/Mapviz%20Setup.docx) :
    
    sudo cp -f ~/Gazebo/rhinoceROS/src/ros_service/.mapviz_config ~ 

Launch the designated rover from the atreus package:
    
    roslaunch atreus spawn_my_bot.launch

Launch the ros package mapviz:
    
    roslaunch mapviz mapviz.launch

Procedure on how to take the blacklisted coordinates and mark its region is given below:

<img src="https://user-images.githubusercontent.com/45683974/77683058-dd44d800-6fbd-11ea-9fee-c72d3f810695.gif" width="900" height="500">

Take down the coordinates on the bottom right of the mapviz window by hovering your cursor at the desired locations. Input these coordinates in [blacklister](https://github.com/leander-dsouza/Gazebo/tree/master/rhinoceROS/src/ros_service/srv/blacklister.txt) and follow the format of insertion(example provided in file):

    h k h2 k2

Note that after you execute the code, the file format changes to "h k r", where r being the euclidean radius of the points. So either rewrite blacklister again or enter in the "h k r" format.

Now run the service:

    rosrun ros_service globalplanner_service.py

It will prompt for a goal location. Type diligently (example goal location given).

    ENTER GOAL GPS COORDINATES - 38.419366 -110.780977

Wait for the service till the blacklisted regions are plotted on mapviz. Finally run the client.

    rosrun ros_service client.py

#### Voilà!

<img src="https://user-images.githubusercontent.com/45683974/77689641-05d1cf80-6fc8-11ea-8a4c-f7a5551b6a64.gif" width="900" height="500">

Note that the generated path is made in reference to the rover's initial position. To change the rover's position and manually drive it with nothing but arrow keys, run the following command:

    rosrun ros_service driving_key.py
