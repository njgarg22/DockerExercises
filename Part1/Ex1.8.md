```
//Create a `logs.txt` file
~ neeraj$ touch logs.txt
```

```
//Run the image specifying the volume mounting
~ neeraj$ docker run -v $(pwd)/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise
Unable to find image 'devopsdockeruh/first_volume_exercise:latest' locally
latest: Pulling from devopsdockeruh/first_volume_exercise
...
Digest: sha256:0fe91ae116a340214cf013541bd311da7196d34a468e9daf74a8d0fdd3419c78
Status: Downloaded newer image for devopsdockeruh/first_volume_exercise:latest
(node:1) ExperimentalWarning: The fs.promises API is experimental
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
^CClosing file
```

```
//Display the logs showing the secret message
~ neeraj$ cat logs.txt 
Mon, 27 Apr 2020 18:16:11 GMT
Mon, 27 Apr 2020 18:16:14 GMT
Mon, 27 Apr 2020 18:16:17 GMT
Mon, 27 Apr 2020 18:16:20 GMT
Secret message is:
"Volume bind mount is easy"
Mon, 27 Apr 2020 18:16:26 GMT
```
