```
//docker-compose.yml
~ neeraj$ cat docker-compose.yml 
version: '3.5'
services:
    frontendservice:
        image: neeraj/frontendexample
        ports:
            - 5000:5000
        environment:
            - API_URL=http://localhost/api
    backendservice:
        image: neeraj/backendexample
        ports:
            - 8000:8000
        environment:
            - REDIS=redisdb
            - REDIS_PORT=6379
            - DB_USERNAME=neeraj
            - DB_PASSWORD=example
            - DB_HOST=db
        depends_on:
            - db
    redisdb:
        image: redis
    db:
        image: postgres
        restart: unless-stopped
        environment:
            - POSTGRES_USER=neeraj
            - POSTGRES_PASSWORD=example
        volumes:
            - ./database:/var/lib/postgresql/data
    nginx:
        image: jwilder/nginx-proxy
        ports:
            - 80:80
        volumes:
            - /var/run/docker.sock:/tmp/docker.sock:ro
            - ./nginx.conf:/etc/nginx/nginx.conf
```
