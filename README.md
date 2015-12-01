# blockly

blockly is a ROS package that provides web-based visualization and block programming tools for robots and drones.

![](img/blockly-peek.png)
![](img/blockly-code.png)

### Installation:
#### Frontend
```
cd <catkin_ws_root>/src
git clone https://github.com/erlerobot/ros_blockly
cd ros_blockly/frontend
git clone https://github.com/erlerobot/blockly
git clone https://github.com/erlerobot/ace-builds
cd ../scripts

# install apache
sudo apt-get install apache2
# make sure that Apache is running properly in your robot and then
./deploy.sh

```

#### Backend
```
# Install dependencies
sudo pip3 install rosdep rosinstall_generator wstool rosinstall
sudo pip3 install autobahn
cd <catkin_ws_root>
catkin_make_isolated --pkg blockly --install
source install_isolated/setup.bash
rosrun blockly blockly_backend.py

# now go to http://erle-brain-2.local/
#  and start playing!

```

### Create your own blocks
- Open `frontend/demos/blockfactory/index.html`
- Design you own block and then add the metadata to: `frontend/blockly/blocks` and `frontend/blockly/generator`
- Launch `python build.py` to regenerate the blocks.

### License
blockly has been built based on [blockly](http://github.com/erlerobot/blockly), [ACE](http://github.com/erlerobot/ace-builds) and Bootstrap. Refer to their sources for the corresponding licenses.

Unless specified, the rest of the code is freed under a GPLv3 License.

### Documentation
- [Erle Robotics blockly docs](http://erlerobotics.com/docs/ROS/blockly/Intro.html)
- [ROS Wiki](http://wiki.ros.org/blockly)


# Robots where blockly has been implemented:
- [Erle-Spider](http://erlerobotics.com/blog/product/erle-spider-the-ubuntu-drone-with-legs/)
- [Erle-Rover](https://erlerobotics.com/blog/product/erle-rover/) (Work in progress)

Do you need help getting your robot supported? Launch your questions at http://forum.erlerobotics.com.
