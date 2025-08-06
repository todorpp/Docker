In this lab we will use AWS ECS to build multi container enviorment 

Steps Backend:

1 Change the source code for our needs 
line 79 `mongodb://${process.env.MONGODB_USERNAME}:${process.env.MONGODB_PASSWORD}@mongodb:27017/course-goals?authSource=admin`, ----->
`mongodb://${process.env.MONGODB_USERNAME}:${process.env.MONGODB_PASSWORD}@${process.env.MONGODB_URL}:27017/course-goals?authSource=admin`,

2 Add the enviorment variable in the file 

3 Build the image and push it to repository 

4 Create ECS cluster 

5 Create Task definition, for Task Role choose ecsTaskExecutionRole

6 Add Container and map port 80

7 Under Docker configuration tab on command field add node,app.js
