# install Redis-Stack using Docker on Ubuntu 

This guide walks users through the steps to install Redis-Stack using Docker on an Ubuntu system. Redis-Stack combines Redis with a range of additional features such as search, graph, JSON, and time series capabilities.
follow me on [GitHub](https://github.com/dannsb) for more docs.
## install Docker
#### 1.Set up Docker's apt repository.
Copy and run the following commands:
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

#### 2.Install the Docker packages.
To install the latest version, run:
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

#### 3.Verify the Docker Engine installed
This command downloads a test image and runs it in a container. When the container runs, it prints a confirmation message and exits.
```bash
sudo docker run hello-world
```
<br/>

## Run Redis Stack on Docker 
To run redis-stack  run:
```bash
docker run -e REDIS_ARGS="--requirepass redis-stack" redis/redis-stack:latest -p 6379:6379 --name redis-stack
```
* you can replace your **password** with "redis-stack", and also can change **name** or **port**.
<br/>

To **verify** that Redis is running correctly, use the following command:
```bash
docker ps
```

<br/>

### More resources
if you want to read full documentaion see below links:\
https://docs.docker.com/engine/install/ubuntu/<br/>
https://hub.docker.com/r/redis/redis-stack
