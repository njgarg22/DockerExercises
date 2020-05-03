```
~ neeraj$ cat docker-compose.yml 
version: '3.5'
services:
    frontendservice:
        image: neeraj/frontendexample
        ports:
            - 5000:5000
        environment:
            - API_URL=http://localhost:8000
    backendendservice:
        image: neeraj/backendexample
        ports:
            - 8000:8000
        environment:
            - FRONT_URL=http://localhost:5000
            - REDIS=redisdb
            - REDIS_PORT=6379
    redisdb:
        image: redis
```
