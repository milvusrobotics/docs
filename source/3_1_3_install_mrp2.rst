3. Installing MRP2 packages for learning ROS
============================================

MRP2 is a open source robot like most of other the other ROS Ready robots. It has public repositories on github. To install those, first navigate to your workspace's ``src`` folder:

::
	
	$ cd ~/catkin_ws/src

Then run these commands one by one:

::
	
	$ git clone https://github.com/milvusrobotics/mrp2_common.git
	$ git clone https://github.com/milvusrobotics/mrp2_desktop.git
	$ git clone https://github.com/milvusrobotics/mrp2_simulator.git

And go to the parent directory (in this case, ``~/catkin_ws``) via that command:

::
	
	$ cd ..

You need to all the rosdep dependencies installed, use the following:

::
	
	$ rosdep install --from-paths src --ignore-src --rosdistro=indigo -y

This command resolves and installs all dependencies for packages inside of your ``src`` folder. Now you can build your packages via ``catkin_make`` command:

::
	
	$ catkin_make

However, These repositories can be improved or changed by Milvus Robotics. If ``catkin_make`` gives an error with some package, You can install that package by hand via trying to write its name:

::
	
	$ sudo apt-get install ros-indigo-<NAME OF THE PACKAGE WHICH GIVES AN ERROR>

Otherwise, you can use web search to find package name.

.. note::
	
	Just start to typing name, and press tab key. If it found the package, pressing tab key completes the command. If there are multiple possible packages, double press to tab key then it will print sutable package names. You can try this feature by writing command below and press tab key:

	::
		
		sudo apt-get install lov

	And try double pressing to tab key with this:

	::
		
		sudo apt-get install morse

	You can install these packages if you want, or simply delete them from you command line after this experiment.