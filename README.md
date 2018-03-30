# HyperStake
HyperStake Docker file to create docker images of hyperstake



## First step - Install docker

To install docker on any linux computer run: 
```
curl -sSL https://get.docker.com | sh
```

For windows, download the docker installer from docker.com and install it


## Second step - Install HyperStake

depending on your linux hardware i have built a number of images

Raspberry Pi/ARM: 
```
docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-raspbian
```

ARM7: 
```
docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-armv7hf-debian
```

AARCH64: 
```
docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-aarch64-debian
```

Ubuntu: 
```
docker run --name hyperstake -v ~/.HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-ubuntu
```

Windows: 
```
docker run --name hyperstake -v %AppData%\HyperStake:/root/.HyperStake  -it -d -p 18775:18775 mcna/hyperstake:v1.1.4-ubuntu
```

## Third step - creating HyperStake.conf
### Windows: 
go to "%AppData%\HyperStake" and create a file called "HyperStake.conf"

### Ubuntu/Raspberry Pi/ARM/Linux
create a file called "~/.HyperStake/HyperStake.conf".

command: 
```
vi ~/.HyperStake/HyperStake.conf
```

### HyperStake.conf content
write the text below into the "HyperStake.conf" file but change the user and password:

rpcuser=##Random user##

rpcpassword=##Random password##

## Four step - Start HyperStake
start HyperStake with command: docker start hyperstake

## Interacting with HyperStake
to interact with hyperstake you will need to use the "docker exec" command, here are some examples:
```
docker exec hyperstake hyperstaked getinfo
```
```
docker exec hyperstake hyperstaked getstakinginfo
```
```
docker stop hyperstake
```
```
docker start hyperstake
```
