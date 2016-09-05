1. Installation of Indigo Version
=================================

1.1. Configure Repositories
---------------------------

If you aren't installed Ubuntu normally, and/or changed repo settings, Configure your Ubuntu repositories to allow ``restricted``, ``universe``, and ``multiverse``. You can follow the `Ubuntu guide <https://help.ubuntu.com/community/Repositories/Ubuntu>`_ for instructions on doing this. Otherwise, directly pass to next section below.

1.2. Setup your sources.list
----------------------------

Just paste this command to your terminal and enter current user's password;

::
	
	$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

1.3. Set up your keys
---------------------

::
	
	$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net --recv-key 0xB01FA116

You can try the following command by adding :80 if you have ``gpg: keyserver timed out`` error;

::
	
	$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

1.4. Installation
-----------------

First, make sure your Debian package index is up-to-date;

::
	
	$ sudo apt-get update

If you are using Ubuntu Trusty 14.04.2 and experience dependency issues during the ROS installation, you may have to install some additional system dependencies.

::
	
	$ sudo apt-get install --install-recommends linux-generic-lts-vivid xserver-xorg-core-lts-vivid xserver-xorg-lts-vivid xserver-xorg-video-all-lts-vivid xserver-xorg-input-all-lts-vivid libwayland-egl1-mesa-lts-vivid libgl1-mesa-glx-lts-vivid libglapi-mesa-lts-vivid libgles1-mesa-lts-vivid libegl1-mesa-lts-vivid xserver-xorg-dev-lts-vivid mesa-common-dev-lts-vivid libxatracker-dev-lts-vivid libgles2-mesa-dev-lts-vivid libgles1-mesa-dev-lts-vivid libgl1-mesa-dev-lts-vivid libgbm-dev-lts-vivid libegl1-mesa-dev-lts-vivid

There are many different libraries and tools in ROS. We provided four default configurations to get you started. You can also install ROS packages individually. If you are not interested with that, just type:

::
	
	$ sudo apt-get install ros-indigo-desktop-full

and confirm, and wait for completition of installation process.

1.5. Initialize rosdep
----------------------

Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS.

First enter;

::
	
	$ sudo rosdep init

After that, enter;

::
	
	$ rosdep update

1.6. Environment setup
----------------------

It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:

::
	
	$ echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc

than;

::
	
	$ source ~/.bashrc
