```
//Dockerfile
neeraj $ cat Dockerfile 
FROM devopsdockeruh/overwrite_cmd_exercise
CMD ["-c"]
```

```
//Build image & run it
docker build -t docker-clock .
docker run docker-clock
```
