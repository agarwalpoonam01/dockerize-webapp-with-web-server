# Smartcow Assignment

### Task 1 - Dockerize the Application
#### Assumptions
* Your base OS is Centos and you have sudo access and open internet connectivity
* Docker is already installed, if not please use the below steps to install the dependencies
```
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install -y python3 python3-pip npm yum-utils device-mapper-persistent-data lvm2 docker-ce docker-compose
sudo systemctl start docker
sudo systemctl status docker
sudo systemctl enable docker
sudo groupadd docker
sudo usermod -aG docker $USER
```
* Logout and login again and validate if you can run docker commands without sudo
```
docker run hello-world
```

##### Things that were added to the code base
* Updated the requirements.txt file with the dependencies and their versions
* Updated the React application so that the DNS resolution is not being done at the client end. The below code snippets were replaced in the sys-stat application in the App.js file
```
const res = await fetch('/stats');
```
* Created Dockerfile for the respective applications(api, sys-stats)
* Created the docker-compose.yaml file with the correct set of dependencies
* Created .gitignore file to ignore node modules
* Created .dockerignore to ensure node modules are not being picked up during the docker build

#### Why I choose the specific Ubuntu image for building my application:
* Ubuntu Image Due to less size as compared to Python based base image
* User is 785(nobody)
* Entrypoint has been used to prevent command override
* Resource chaining has been implemented in the Dockerfile to reduce the number of Docker layers which helps in keeping a check on the Docker image size

#### I've created 3 images and published them to the Docker Hub:
* poonamag/smartcow-webapp
* poonamag/smartcow-react
* poonamag/smartcow-nginx

#### You can use the below command to bring up the docker-compose stack
* The docker compose file is present 
```
docker-compose up -d
```
