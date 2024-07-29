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
 
d.	Optionally, we can use the below command to run the docker image and start Nginx on port 80.
i.	sudo docker run -d -p 80:80 my-nginx-image
e.	Check the docker container
i.	sudo docker ps
f.	check web page running on port 80

 
5.	Push the image on ECR
a.	Install “AWS CLI” on ubuntu and configure it using AWS Access Key
i.	sudo apt install awscli
ii.	sudo aws configure
b.	Go to AWS Amazon Elastic Container Registry and create a public repository.
 
c.	Click on repository and check the command to push the image to this repo.
d.	Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI:
i.	sudo aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/f8g8h5d4
e.	Build your Docker image using the following command.
i.	sudo docker build -t muzahid_custom_nginx_repo .
f.	After the build completes, tag your image so you can push the image to this repository:
i.	sudo docker tag muzahid_custom_nginx_repo:latest public.ecr.aws/f8g8h5d4/muzahid_custom_nginx_repo:latest
g.	Run the following command to push this image to your newly created AWS repository:
i.	sudo docker push public.ecr.aws/f8g8h5d4/muzahid_custom_nginx_repo:latest


