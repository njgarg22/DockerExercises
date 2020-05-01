```
//The images for `frontend` & `backend` were built in Part1 exercises.
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
```            
