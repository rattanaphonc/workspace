#!/bin/bash

############# BUILD IMAGE #############

export IMAGE=torch_notebook:1.13.1
docker build . -t $IMAGE

############# EDIT HERE #############
export CONTAINER_NAME=torch_notebook
export GPUS='"device=0"'
export MEMORY=38GB
export CPU=16
export SERVER_MOUNT_POINT=~/top_workspace
export CONT_MOUNT_POINT=/mount
export PASSWORD=passwd
export PORT=8855
#####################################

docker run -it --name $CONTAINER_NAME \
           --gpus $GPUS --memory=$MEMORY --cpus=$CPU \
           -v $SERVER_MOUNT_POINT:$CONT_MOUNT_POINT \
           -w $CONT_MOUNT_POINT \
           --device /dev/fuse \
           --cap-add SYS_ADMIN \
           --privileged \
           -p $PORT:8888 \
           -e JUPYTER_TOKEN=$PASSWORD \
           $IMAGE
