REALSENSE_DIRECTORY=realsense-container/
REALSENSE_IM_NAME=lmwafer/realsense-ready
REALSENSE_IM_TAG=2.5-ubuntu18.04
REALSENSE_CONT_NAME=realsense-container

ORB_DIRECTORY=orb-container/
ORB_IM_NAME=lmwafer/orb-slam-3-ready
ORB_IM_TAG=1.0-ubuntu18.04
ORB_CONT_NAME=orb-3-container # You will need to apply the exact same name to container_name in orb-container/docker-compose.yml

ROS_NODE_DIRECTORY=ros_node-container/
ROS_NODE_IM_NAME=markselias/orbslam3-ros_node-ready
ROS_NODE_IM_TAG=1.0-ubuntu18.04
ROS_NODE_CONT_NAME=orbslam3-ros_node-container

default: up-orb enter-orb


up-orb:
	sudo xhost +local:root && cd ${ORB_DIRECTORY} && sudo docker-compose up -d

enter-orb:
	clear && docker exec -it ${ORB_CONT_NAME} bash

down-orb:
	cd ${ORB_DIRECTORY} && docker-compose down

build-orb:
	cd ${ORB_DIRECTORY} && sudo docker build -t ${ORB_IM_NAME}:${ORB_IM_TAG} .


up-realsense:
	sudo xhost +local:root && cd ${REALSENSE_DIRECTORY} && sudo docker-compose up -d

enter-realsense:
	clear && docker exec -it ${REALSENSE_CONT_NAME} bash

down-realsense:
	cd ${REALSENSE_DIRECTORY} && docker-compose down

build-realsense:
	cd ${REALSENSE_DIRECTORY} && sudo docker build -t ${REALSENSE_IM_NAME}:${REALSENSE_IM_TAG} .

up-ros_node:
	sudo xhost +local:root && cd ${ROS_NODE_DIRECTORY} && sudo docker-compose up -d

enter-ros_node:
	clear && docker exec -it ${ROS_NODE_CONT_NAME} bash

down-ros_node:
	cd ${ROS_NODE_DIRECTORY} && docker-compose down

build-ros_node:
	cd ${ROS_NODE_DIRECTORY} && sudo docker build -t ${ROS_NODE_IM_NAME}:${ROS_NODE_IM_TAG} .
