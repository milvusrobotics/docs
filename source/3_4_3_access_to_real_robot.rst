3. Access to Control of Your Real Robot
=======================================

Start real robot and control it!

1. Power up
-----------

To power up the robot, all you need to do is to press power button on the user panel. The button should flash for a few seconds until the system boots and robot becomes ready to use. When the power light becomes solid, you can start using the robot.

2. Access the robot
-------------------


First be sure the robot and your PC are connected the same network. To join the ROS network of MRP2 from your own PC, you should run just two commands to change your currently opened terminal's settings. You must run this commands everytime when you opened a new terminal:

.. warning::

    Don't forget to replace ``<IP_OF_...>`` sections with real ip's.

::

    $ export ROS_MASTER_IP=http://<IP_OF_MRP2_ONBOARD_COMPUTER>:11311


::

    $ export ROS_HOSTNAME=<IP_OF_YOUR_PC>

Otherwise add these lines to your ``.bashrc`` file by: 

::

    $ echo "export ROS_MASTER_IP=http://<IP_OF_MRP2_ONBOARD_COMPUTER>:11311" >> ~/.bashrc

::

    $ echo "export ROS_HOSTNAME=<IP_OF_YOUR_PC>" >> ~/.bashrc

After writing these lines to your ``.bashrc`` file, run:

::

    $ source ~/.bashrc

command once. 

Now, if you'll launch a ros process from that terminal, it communicates with Robot's ``ros_master`` process. You can control your robot via running ``rqt_robot_steering``  application on that terminal. Or if the one of the navigation demos is running on the robot side, you can simply run Rviz application of ``gmapping`` or ``amcl``. It will read the datas from robot's topics. If you don't know how to run ``gmapping`` or ``amcl`` process on robot side, don't worry about it, We'll teach you in next tutorial.

.. note::
	
	When you added these lines to your ``.bashrc`` file, you don't need to source everytime. That file is already sourcing when the terminal client starts up. Note that, If these lines are added the your ``.bashrc`` file, You won't be able to launch local ROS  applications like Gazebo Simulation on your PC. Before launching local applications, you need to run these  commands, They clear ``ROS_HOSTNAME`` and ``ROS_MASTER_IP`` variables like a described in previous tutorials:

	::

		$ export ROS_MASTER_IP= $$ export ROS_HOSTNAME=
   
You can start moving robot via joystick or what you prefer to control as a described in previous tutorials after it boots up. For example If you want to control it via ``rqt_robot_steering``, open up new terminal tab on your remote PC's terminal, and run ``rqt_robot_steering``:

::
		
	$ rosrun rqt_robot_steering rqt_robot_steering 

If that launch gives an error, Check the ``ROS_HOSTNAME`` and ``ROS_MASTER_IP`` variables.