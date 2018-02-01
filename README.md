# collect data

#for maximum performance 

#Open terminal
sudo nvpmodel -m 2
sudo ~/jetson_clocks.sh

#for observing performance
sudo ~/tegrastats


#Open Joystick.  When you use vibration button you can check if it works or not. 

#Open new terminal
sudo mv /dev/input/js1 /dev/input/js0
cd racecar-ws
source devel/setup.bash
roslaunch racecar teleop.launch


#Open new terminal
cd racecar-ws
source devel/setup.bash
rosrun deep_learning collect_data.py

#For autonomous mode
rosrun deep_learning predict.py

#Write this code on terminal
ps -ef | grep predict.py



