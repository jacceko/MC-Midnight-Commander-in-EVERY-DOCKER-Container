**Midnight-Commander-in-EVERY-DOCKER-Container**

Script in bash for Auto exec/install Midnight Commander in your apps dockers containers - Every containers based on debian/alpine/centos/ubi/ubuntu)

If you ever want to copy files inside working container or to/from container to host in easy way, you may want to have mc in every container.

**USAGE**

	Before first use: chmod u+x mcd.sh

	Normal usage: ./mcd.sh CONTAINER_NAME

	Example:      ./mcd.sh nginx

 
**HOW IT WORK:**

This script execute mc in container if mc not exist, mc will be installed in proper way depend on system debian/ubi/alpine/centos/ubuntu and then execute mc

If all work ok - you will see mc blue screen and on bottom you see root@docker-xxxxx some number - this mean your mc are in docker

To copy files from to outside docker in docker you can add volume name for ex. "/exchange" - mapped to your host system local folder to use it for exchange with all your docker containers
