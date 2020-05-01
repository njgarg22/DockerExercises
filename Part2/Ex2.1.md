```
//Pull the image for service defined in compose file.
~ neeraj$ docker-compose pull
Pulling volumeexercise ... done
```

```
//create an empty logs.txt
~ neeraj$ touch logs.txt
```

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
