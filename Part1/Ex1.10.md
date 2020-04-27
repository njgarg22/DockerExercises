```
//clone the project
~ neeraj$ git clonehttps://github.com/docker-hy/frontend-example-docker.git
```

```
//Dockerfile
FROM node:10

WORKDIR /usr/src/app

COPY package.json .
COPY package-lock.json ./

RUN npm install 

COPY . .

EXPOSE 5000

CMD ["npm", "start"]
```

```
//Build the image
~ neeraj$ docker build -t neeraj/frontendexample .
```

```
//Run the image in a container
~ neeraj$ docker run -p 5000:5000 -d neeraj/frontendexample
```

```
//Check the results in the browser
http://localhost:5000/
```
