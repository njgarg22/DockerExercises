```
~ neeraj$ cat docker-compose.yml
version: '3.5'
services:
    frontend:
        build: ./ml-kurkkumopo-frontend
        container_name: ex_frontend
        ports:
            - 3000:3000
    backend:
        build: ./ml-kurkkumopo-backend
        container_name: ex_backend
        ports:
            - 5000:5000
        volumes:
            - model:/src/model
        depends_on:
            - training
    training:
        build: ./ml-kurkkumopo-training
        container_name: ex_training
        volumes:
            - images:/src/imgs
            - csv:/src/data
            - model:/src/model
volumes:
    images:
    csv:
    model:
```
