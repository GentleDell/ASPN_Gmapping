This gmapping program give out two documents including the pose of robot.
The pose of robot when the map is update is saved into map_pose.txt.
The pose when the scan_match is done is saved into scan_pose.txt.
Before you run or launch this program, you need change the path to your own in the line 129-169 of gmapping/src/slam_gmapping.cpp.

输出两个txt文件存储机器人的位姿；
map_pose.txt中存储更新地图时利用的位姿
scan_pose.txt中存储每次匹配得到的位姿
使用本程序时需要先将gmapping/src/slam_gmapping.cpp中129-169行中的存储路径修改为你自己的路径。