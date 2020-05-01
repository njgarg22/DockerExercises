```
//docker-compose.yml
~ neeraj$ cat docker-compose.yml 
version: '3.5' 

services: 

    volumeexercise: 
      image: devopsdockeruh/first_volume_exercise 
      build: . 
      volumes: 
        - ./logs.txt:/usr/app/logs.txt
      container_name: volumeex
```      
