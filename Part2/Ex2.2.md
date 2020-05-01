```
~ neeraj$ cat docker-compose.yml 
version: '3.5'
services:
    portsexercise:
        image: devopsdockeruh/ports_exercise
        ports:
            - 80:80
```            
