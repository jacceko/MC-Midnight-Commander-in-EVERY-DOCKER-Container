#!/bin/sh
# usage: ./mcd COINTAINER_NAME
#
# This script execute mc in container if mc not exist, mc will be installed depend on system debian/ubi/alpine/centos/ubuntu and then execute mc
# If all work ok - you will see mc blue screen and on bottom you see root@docker-xxxxx some number - this mean your mc are in docker
#
# To copy files from/to outside docker in docker you can add volume name for ex. "/exchange" - mapped to your host system local folder
#
if ! docker exec -it $1  /bin/sh -c "command -v mc" >/dev/null 2>&1; then
	if docker exec -it $1  /bin/sh -c "command -v apt" >/dev/null 2>&1; then
		echo "MC not Found - install mc by apt-get - debian/ubuntu"
		docker exec -it $1 /bin/sh -c "apt-get update && apt-get install -y mc &&  mc"
    elif docker exec -it $1  /bin/sh -c "command -v apk" >/dev/null 2>&1; then
		echo "MC not Found - install mc by apk - alpine"
		docker exec -it $1  /bin/sh -c "apk add --no-cache mc && mc"
	elif  docker exec -it $1  /bin/sh -c "command -v yum" >/dev/null 2>&1; then
		echo "MC not Found - install mc by yum - ubi/centos"
		docker exec -it $1  /bin/sh -c "yum update && yum install -y mc && mc"		
    fi
else
    echo "MC found"
    docker exec -it $1 /bin/bash -c "mc"
fi


