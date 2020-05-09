```
//nginx conf file
~ neeraj$ cat nginx.conf 
  events { worker_connections 1024; }

  http {
    server {
      listen 80;

      location / {
        proxy_pass http://frontendservice:5000/;
      }

      location /api/ {
        proxy_pass http://backendservice:8000/;
      }
    }
  }
```

```
//docker-compose file
~ neeraj$ cat docker-compose.yml 
version: '3.5'
services:
    frontendservice:
        image: neeraj/frontendexample
        ports:
            - 5000:5000
        environment:
            - API_URL=http://localhost:8000
    backendservice:
        image: neeraj/backendexample
        ports:
            - 8000:8000
        environment:
            - FRONT_URL=http://localhost:5000
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
    nginx:
        image: jwilder/nginx-proxy
        ports:
            - 80:80
        volumes:
            - /var/run/docker.sock:/tmp/docker.sock:ro
            - ./nginx.conf:/etc/nginx/nginx.conf
```
