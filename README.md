# HyperStake
HyperStake Docker file to create docker images of hyperstake



First step - Install docker
To install docker on any linux computer run: curl -sSL https://get.docker.com | sh

For windows, download the docker installer and install it

Second step - Install HyperStake

depending on your linux hardware i have built a number of images

Raspberry Pi/ARM: docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-raspbian

ARM7: docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-armv7hf-debian

AARCH64: docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-aarch64-debian

Ubuntu: docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-ubuntu

Windows: docker run --name hyperstake -v %AppData%\HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-ubuntu


the commands above will put the HyperStake data folder in the default location for the OS, e.g. windows "%AppData%\HyperStake", linux "~/.HyperStake"



to instact with hyperstake you will need to use the "docker exec" command, here are some examples:

docker exec hyperstake hyperstaked getinfo

docker exec hyperstake hyperstaked getstakinginfo

docker stop hyperstake

docker start hyperstake
