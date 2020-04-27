```
//clone the project
~ neeraj$ git clone https://github.com/docker-hy/backend-example-docker.git
```

```
//Dockerfile
From node:10
WORKDIR /usr/src/app
COPY package.json .
COPY package-lock.json .
RUN npm install
COPY . .
EXPOSE 8000
CMD ["npm", "start"]
```

```
//Build the image
~ neeraj$ docker build -t neeraj/backendexample .
```

```
//Create an empty file called logs.txt
touch logs.txt
```

```
//Run the image in a container
~ neeraj$ docker run -p 8000:8000 -v $(pwd)/logs.txt:/usr/src/app/logs.txt -d neeraj/backendexample
```

```
//Check the results in the browser
http://localhost:8000/
```

```
//Display logs.txt file
~ neeraj$ cat logs.txt

4/27/2020, 8:45:00 PM: Connection received in root
4/27/2020, 8:45:42 PM: Connection received in root
4/27/2020, 8:45:48 PM: Connection received in root
```
