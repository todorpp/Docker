In this lab we will use AWS ECS to build multi container enviorment 

Steps Backend:

1 Change the source code for our needs 
line 79 `mongodb://${process.env.MONGODB_USERNAME}:${process.env.MONGODB_PASSWORD}@mongodb:27017/course-goals?authSource=admin`, ----->
`mongodb://${process.env.MONGODB_USERNAME}:${process.env.MONGODB_PASSWORD}@${process.env.MONGODB_URL}:27017/course-goals?authSource=admin`,

2 Add the enviorment variable in the file and in the Docker file

3 Build the image and push it to repository 

4 Create ECS cluster 

5 Create Task definition, for Task Role choose ecsTaskExecutionRole

6 Add Container and map port 80

7 Under Docker configuration tab on command field add node,app.js

8 Add the enviorment variables as key-value pair / MONGODB_URL value must be localhost for this field /

Steps Mongodb:

1 Create new container using image mongo

2 Map port 27017 , and add mongo enviorment variables credentials

3 Create service inside the cluster tab , add the task definition, choose the VPC which was created while creating the cluster include the subnets, and select Application Load Balancer

4 In Configure Routing step choose Target type - IP , and choose the corect security group

5 To avoid problems with the Load Balancer,  Health check path must be set to /goals 

6 We can verify if everything is working visiting the Public IP, also we can use Postman to send POST and GET requests on x.x.x.x/goals

7 Go to EFS and create new file system, paralel with that create new security group and add it to the VPC , and create Inbound rule with type NFS and link it to the other security group which is for the containers on port 2049
and for the EFS choose the new security group

8 In Task Definition Create new revision, and Add Volume and pick EFS type with the files system which we created

9 Go to the mongodb container and in the Mount points type /data/db this is the path where mongdb will write 

