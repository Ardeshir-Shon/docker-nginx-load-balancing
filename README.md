# Docker Nginx Load Balancing
Use Nginx with multiple Node.js web server to try load balancing in Docker

## Project Structure
The project structure of the repo.
```
.
|____app
| |____Dockerfile
| |____package.json
| |____server.js
|____nginx
| |____Dockerfile
| |____nginx.conf
|____docker-compose.yml
```

## Build
Build up the service.
```
$ docker-compose up --build
```

## Hello Nginx
You can test the load balancing of nginx by opening the localhost:5200 on your browser.


### K6 Load Testing
Script.js file is added to hit the endpoint we configured a load balancer to. You can run the following command to perform a load test:
```
$ k6 -u [number_of_simuntaneous_users] -d [hit_period_duration_in_seconds]s --out json=log.json script.js 
```
