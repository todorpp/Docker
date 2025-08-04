This lab consist Laravel & PHP Setup and multi container enviorment 
Review slides-laravel.pdf 

On nginx.conf line 12 we must set the port 
12 fastcgi_pass php:9000;

Launch containers separetly , artisan need the "migrate" command 

docker-compose up -d server php mysql 
docker-compose run --rm artisan migrate
