# publish_pointcloud
'''
功能描述:将loam运行时输出的地图消息转化为二维占据栅格地图并加以保存

本功能包中所写的节点是将loam运行发布的地图数据绕x轴旋转90度再重新发布，使得二维地图能够正确投影，承担地图消息转化任务的是octomap_server
'''
# 准备工作
'''
   1、安装ocotomap
   sudo apt-get install ros-kinetic-octomap-ros #安装octomap
   sudo apt-get install ros-kinetic-octomap-msgs
   sudo apt-get install ros-kinetic-octomap-server
   sudo apt-get install ros-kinetic-octomap-rviz-plugins #安装octomap在rviz中的插件

   2、安装loam
   cd catkin_ws/src
   git clone https://github.com/daobilige-su/loam_velodyne.git
   cd ..
   catkin_make
   (这里直接编译可能会提示缺少loam.test.in文件，所以在编译之前/loam_velodyne目录下建立tests文件夹，在/tests文件夹下新建一个loam.test.in空白文件)

   3、确保你下载并安装了omtb，或下载相关数据集
   
'''
# 下载安装

   cd catkin_ws/src

   git clone https://github.com/HITROS/LoamMap.git

   cd ..

   catkin_make

# 启动转化节点
   可以运行数据集或在omtb中实验
   1、运行数据集
    将octo_loam_dataset.launch中的数据集路径改为你计算机上的路径
    roslaunch publish_pointcloud octo_loam_dataset.launch
   2、运行omtb
   roslaunch publish_pointcloud octo_loam_omtb.launch
    

