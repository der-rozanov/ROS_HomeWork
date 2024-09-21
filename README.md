# ROS_HomeWork

Робот тредставляет собой 5dof манипулятор. Все звенья вращательные. Первые 3 джоинта представляют собой трехзвенный манипулятор, остальные два играют роль запятья. Симуляция происходит на базе симулятора Gazebo, через лаунч файл arm_gazebo_control.launch. Геометрия джоинтов прописана в папке meshes в виде STL файле.

Структура робота так же описана в URDF tree фалйе который находится в папке URDF. 

Управление роботом происходит либо с попомщью публикации сообщений через консоль формата 

  rostopic pub /arm_controller/command trajectory_msgs/JointTrajectory '{joint_names: ["arm_base_joint","shoulder_joint", "bottom_wrist_joint", "elbow_joint","top_wrist_joint"], points: [{positions: [0, -0.2, 1, 0, 0], time_from_start: [1,0]}]}' -1

Либо через Python скрипт control.py 
