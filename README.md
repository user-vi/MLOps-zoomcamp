# MLOps-zoomcamp
1) open AWS Console Home and create EC2 instance
2) open Instance in menu and choose Launch an Instance. 
2.1) Create name and choose Ubuntu 64-bit(x86). 
2.2) Select instance with 8GiB Memory
2.3) Create new key pair. Choose RSA key and *.pem and move to ~/.ssh
2.4) Fill storage configuration (30GiB - is ok)
2.5) Click on Launch instance
3) open Instance in menu and click on InstanceID
```
chmod 400 ~/.ssh/mlops-zoomcamp.pem
ssh -i ~/.ssh/mlops-zoomcamp.pem ubuntu@{Public_IPv4_address}

wget https://repo.anaconda.com/archive/Anaconda3-2023.03-1-Linux-x86_64.sh
bash Anaconda3-2023.03-1-Linux-x86_64.sh 

sudo apt update
sudo apt install docker.io

mkdir ./soft
cd ./soft
wget https://github.com/docker/compose/releases/download/v2.18.1/docker-compose-linux-x86_64 -O docker-compose
chmod +x docker-compose

cd ..
vim .bachrc
export PATH="${HOME}/soft:${PATH}" #add string
source .bachrc

sudo docker run hello-world 

# docker without sudo https://docs.docker.com/engine/install/linux-postinstall/
sudo groupadd docker
sudo usermod -aG docker $USER
logout


```

4) open VScode and connect to remote machine using remoteSSH extention
5) set up port forwarding: go to PORTS in VScode and set port=8888


```
mlflow ui --backend-store-uri sqlite:///mlflow.db
```
