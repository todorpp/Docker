In this project we will deploy containers into AWS remote machines . 

Containerized apps might need a build step (React apps) .

Multi container projects might need to be split acress multiple hosts .

Bind Mounts shouldn't be used as this simulates Production .

Objectives:
1 Create and launch EC2 instance, VPC and security group

2 Configure security group to expose all required ports to WWW

3 Connect to instance via SSH , install Docker and run cantainer

Steps:
1 Create EC2 instance and key pair

2 Connect via SSH

3 Install Docker:
sudo yum update -y
sudo yum -y install docker
sudo service docker start
sudo usermod -a -G docker ec2-user
Log out with Ctrl + D and log in again 
sudo systemctl enable docker
docker version

4 Upload the builded image with the source code inside a repository

5 Run on EC2 instance sudo docker run -d --rm -p 80:80 todorparushev/project1

6 Create rule in the security group allowing HTTP traffic

7 Visit the public IP of the instance to verify the connection








