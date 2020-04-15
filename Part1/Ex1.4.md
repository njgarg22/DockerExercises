```
C02Y10B4JGH5:~ i342116$ docker run -d --name bashex devopsdockeruh/exec_bash_exercise
Unable to find image 'devopsdockeruh/exec_bash_exercise:latest' locally
latest: Pulling from devopsdockeruh/exec_bash_exercise
741437d97401: Pull complete 
34d8874714d7: Pull complete 
0a108aa26679: Pull complete 
7f0334c36886: Pull complete 
65c95cb8b3be: Pull complete 
a36b708560f8: Pull complete 
4090f912e6c7: Pull complete 
ce5fe2607c2e: Pull complete 
9400f5f657d6: Pull complete 
c4919883f7fa: Pull complete 
Digest: sha256:c463832132d1fb0b8b3b60348a6fc36fda7512a4ef2d1050e8bea7b6a6d7a2f3
Status: Downloaded newer image for devopsdockeruh/exec_bash_exercise:latest
46997c6d23d64fcb208ce51eac6b1564048b80b1fe4504476f4dbf2259171f2b


C02Y10B4JGH5:~ i342116$ docker exec -it bashex bash
root@46997c6d23d6:/usr/app# tail -f ./logs.txt
Wed, 15 Apr 2020 21:10:04 GMT
Secret message is:
"Docker is easy"
```
