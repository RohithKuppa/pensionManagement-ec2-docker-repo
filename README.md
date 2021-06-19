# How to install and use Docker on AWS EC2


1. Launch a new ec2 instance
2. save the key to your local machine
3. install putty
4. generate ppk from pem and save it
5. run putty and mention the public ip address of ec2
6. add ssh->auth->browse->add the saved ppk file
7. open
--------------------------------------------------------------------------------------------------------
installing docker on ec2

1. sudo yum update -y
2. sudo yum install docker -y
3. sudo service docker start
4. Add ec2-user to the docker group 
sudo usermod -a -G docker ec2-user
5. docker  -v

------------------------------------------------------------------------------------------------------------

#Installing Java

sudo amazon-linux-extras install java-openjdk11

Transferring files from Local Machine to EC2:
1) Create s3 bucket and add the files to be coppied
2) Allow public access to the files
3) Copy the object URL of the fils in S3
4) RUN wget "paste-url"

How to build images from the jar file:
Follow steps from docker-repository

* Modify the inbound rule and add All Port Range dor All Protocol to All
* Use http rather https
--------------------------------------------------------------------------------------------------------------------

#Dockerfile for building image for java application


FROM adoptopenjdk/openjdk11
WORKDIR /
ADD truyum-app.jar truyum-app.jar
EXPOSE 5000
CMD java -jar truyum-app.jar



