# ros2的基础学习

## 前置条件
|ROS2 Humble| [download](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html)|
|---|---|
```bash
#下载后，需要输入以下命令
source /opt/ros/humble/setup.bash
```
> 也可以将其写入用户配置文件中(.bashrc)
```bash
#打开.bashrc
gedit ~/.bashrc
```
> 在末尾加入"source /opt/ros/humble/setup.bash"这句指令
## 1.安装ros2的构建工具("colcon")
```bash
#Installation
sudo apt update
```
```bash
#then
sudo apt install python3-colcon-common-extensions
```
```bash
#建议额外操作
cd /usr/share/colcon_arcomplete/hook/
gedit ~/.bashrc
#然后在结尾加入"source /usr/share/colcon_arcomplete/hook/"
```
```bash
#then
source ~/.bashrc
```
## 2.建立工作区
```bash
cd
mkdir tlt_ws
#"_ws" means "workspace"
```
```bash
cd tlt_ws
mkdir src
colcon build
source ~/tlt_ws/install/setup.bash
#colcon build后你会发现多了几个文件夹和文件
```
```bash
gedit .bashrc
#在结尾加入"source ~/tlt_ws/install/setup.bash"
```
## 3.建立工作包
```bash
cd tlt_ws/src/
ros2 pkg create your_package_name --build-type ament_python --dependencies rclpy
#rclpy is a python library for ros2
```
> 如果没有安装Vitual Studio Code
```bash
#download VSCode
sudo snap intall code --classic
```
```bash
#open the workspace in VS Code
code .
```
```bash
#返回上一级("tlt_ws")
cd ..
#build the package
colcon build
```
> 如果报错了
```bash
cd
sudo apt install python3-pip  #download the pip tool
pip3 install setuptools==58.2.0   #将setuptools的版本设置为58.2.0
#完成上述报错的操作
cd tlt_ws
colcon build
```
## 后续编写代码相关
[视频教程](https://www.youtube.com/watch?v=0aPbWsyENA8&list=PLLSegLrePWgJudpPUof4-nVFHGkB62Izy&index=1)
