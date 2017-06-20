Gmapping for ASPN
Based on Gmapping. Please see https://github.com/ros-perception/slam_gmapping.git

This gmapping program give out data about the pose of robot with the format like: time, x, y theta, and it openes and closes both files everytime when it is going to writing.  We only use the first constructor of SlamGMapping.

The pose of robot when the map is updated is saved into map_pose.txt.
The pose when the scan_match is done is saved into scan_pose.txt.
Before launch this program, you need change the path to your own in the lines 137,149,668 and 804 of gmapping/src/slam_gmapping.cpp.

If you use QT, due to neglecting of CMAKE_PREFIX_PATH and CATKIN_PACKAGE_PREFIX, QT can not import gmapping(or ROS projects) correctly and there are many errors about losing packages(e.g. nav_mags).
Therefore, we need to input the path acoordind to the '.bashrc', in which all of path variables are well setted.

In this computer, we add '.bashrc' with:
	"
	source /opt/ros/kinetic/setup.bash
	export CMAKE_PREFIX_PATH=$CMAKE_PREFIX_PATH:/home/gentle/catkin_ws/devel:/opt/ros/kinetic:/home/gentle/Software/Qt5.8.0/5.8/gcc_64/lib/cmake
	export PATH=$PATH:/home/gentle/Software/Qt5.8.0/Tools/QtCreator/bin:/home/gentle/Software/Qt5.8.0/5.8/gcc_64/bin
	# ROS
	source /home/gentle/catkin_ws/devel/setup.bash
	export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:/home/gentle/catkin_ws/devel
	"

	Then, we fill CMAKE_PREFIX_PATH of QT in /home/gentle/catkin_ws/devel:/opt/ros/kinetic:/home/gentle/Software/Qt5.8.0/5.8/gcc_64/lib/cmake  (also named CMAKE_PREFIX_PATH ) and fill CATKIN_PACKAGE_PREFIX of QT in /home/gentle/catkin_ws/devel	(named ROS_PACKAGE_PATH)
