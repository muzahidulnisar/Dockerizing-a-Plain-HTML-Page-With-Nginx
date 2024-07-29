# Dockerizing-a-Plain-HTML-Page-With-Nginx

## Create basic index.html file.
## Create a “nginx.conf”
## Create a “Dockerfile” 
## Building the Docker Image
  ### Run the below command to install docker
  #### sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
  #### curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add –
  #### sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  #### sudo apt-get update
  #### sudo apt-get install docker-ce
  #### Build docker image using Dockerfile
  #### sudo docker build -t muzahid-nginx-image .
  ### Check created Docker Image
  #### sudo docker image ls
 
###  Optionally, we can use the below command to run the docker image and start Nginx on port 80.
#### sudo docker run -d -p 80:80 my-nginx-image
### Check the docker container
#### sudo docker ps
#### check web page running on port 80

 
## Push the image on ECR
### Install “AWS CLI” on ubuntu and configure it using AWS Access Key
#### sudo apt install awscli
#### sudo aws configure

### Go to AWS Amazon Elastic Container Registry and create a public repository.
### Click on repositiory and check the command to push the image to this repo.
### Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:
### Build your Docker image using the following command.
### After the build completes, tag your image so you can push the image to this repository.
### Run the following command to push this image to your newly created AWS repository.


