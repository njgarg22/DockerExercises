```
//Dockerfile
~ neeraj$ cat Dockerfile 
FROM ubuntu:16.04
RUN apt-get update && apt-get install sudo -y && sudo apt-get install curl -y
COPY curl.sh .
RUN chmod +x curl.sh
CMD ./curl.sh
```

```
//Build the image
~ neeraj$ docker build -t curler .
```

```
//Run the container
~ neeraj$ docker run -it curler
Input website:
helsinki.fi
...
...
```
