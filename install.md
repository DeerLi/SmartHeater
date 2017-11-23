
## Install Docker CE latest stable version

```bash
sudo apt-get remove docker docker-engine docker.io

sudo apt-get update

sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
    
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
   
sudo apt-get update

sudo apt-get install docker-ce


```

## Install Nvidia-docker runtime


## Docker restore image

```bash
docker load --input eth-proxy-dwarf.tar
docker load --input ethminer.tar
```

## Run proxy

```bash
docker run --name proxy -d -p 8080:8080 deerli/eth-proxy:dwarf
```

## Run miner

```
docker run --runtime=nvidia --name em -d -ePOOL=xxx.xxx.xxx.xxx -eNICK=$(hostname) deerli/etherminer:1.3 
```
