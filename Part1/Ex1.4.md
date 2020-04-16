```
//Start the image
:~ neeraj$ docker run -d --name bashex devopsdockeruh/exec_bash_exercise
Unable to find image 'devopsdockeruh/exec_bash_exercise:latest' locally
...
Status: Downloaded newer image for devopsdockeruh/exec_bash_exercise:latest
46997c6d23d64fcb208ce51eac6b1564048b80b1fe4504476f4dbf2259171f2b


//Enter inside container and run `tail` command
:~ neeraj$ docker exec -it bashex bash
root@46997c6d23d6:/usr/app# tail -f ./logs.txt
Wed, 15 Apr 2020 21:10:04 GMT
Secret message is:
"Docker is easy"
```
