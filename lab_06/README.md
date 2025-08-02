This lab consists of three components: database, frontend, and backend. The goals are:

1 Components must be connected
2 Data must persist with the help of volumes
3 Access should be limited
4 Live source code updates for backend and frontend
5 The application is simple — it allows us to store some values in the form of goals.

In line 87 of the backend app’s source code, we must authenticate to MongoDB using environment variables for the username and password. Also, ?authSource=admin is required at the end of the connection string.

mongodb://${process.env.MONGODB_USERNAME}:${process.env.MONGODB_PASSWORD}@mongodb:27017/course-goals?authSource=admin
For the frontend app, we use 'http://localhost/goals' because it's React code that runs in the browser.

Once the code is optimized for our needs, we start by creating the MongoDB container using credentials for authentication and a named volume for data persistence:

docker run --name mongodb -v data:/data/db --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=todor -e MONGO_INITDB_ROOT_PASSWORD=secret mongo
We can then proceed with the backend. Using a bind mount, code changes will be reflected immediately in the running app:

docker run --name goals-backend -v C:\Users\tppar\Desktop\Docker\6th\backend:/app -v logs:/app/logs -v /app/node_modules --rm -d --network goals-net -p 80:80 goals-node

And finally, the frontend:

docker run -v C:\Users\tppar\Desktop\Docker\6th\frontend\src:/app/src --name goals-frontend --rm -d -p 3000:3000 go
