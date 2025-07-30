This lab goal is show how containers communicate via Networks .

The application send REST API requests to dummy website. In order to verify what is happening we must use Postman where we POST key value pairs :

"name": "A new Hope",
    "type": "movie",
    "url": "http://swapi.dev/api/films/1/"

and we are using localhost:3000/favorites . We then can use GET  request to call the stored value into mongodb container. 

Both containers communicate on created Network and the database must be specified in the source code in our example line 71 'mongodb://mongodb:27017/swfavorites', .

Running the containers with the following syntax commands : 

docker network create favorites-net

docker run -d --name mongodb --network favorites-net mongo

docker run --name favorites --network favorites-net -d --rm -p 3000:3000 favorites-node


