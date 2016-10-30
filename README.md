# ROS-I_hardware_drivers
ROS-Industrial  combining ROS combines high-level functionality with the low-level reliability and safety of industrial robot controllers.
In general, almost all modern industrial robot platforms provides interfaces for users to communicate with controllers, and that is the reason why ROS-industrial was developed. Currently, industrial manipulators, like ABB, Kuka, Adept, Fanuc, Motoman, and Universal Robots are supported by ROS-Industrial packages, and this length of list is still increasing.

This repositoty is a collections of very low level communication protocols and developed software interfaces, enabling applications to access and operate physical robot, sensors(Kinect, Leap Motion, et al). 

And in our study, we defined a standardized interface template with general operation service type:
API template
  bool GetRobots(std::vectorhinti robots);
  bool Login(const std::string url, const std::stringuserName, const std::string password);
  bool GetRobotJoints(std::vectorhdoublei joints);
  bool GetRobotCartesianPosition(std::vectorhdoubleiposition);
  bool SetJoints(const std::vectorhdoublei joints);
  bool MoveL(std::vectorhdoublei pos);
  bool MoveJ(std::vectorhdoublei pos);
  
 motion commander/commander.msg
  uint8 command index
  std msgs/Header header
  float32[] position
  float32[] orientation
  float32[] joints
  - - -
  uint8 resultstd msgs/Header header
  float32[] position
  float32[] orientation
  float32[] joints
