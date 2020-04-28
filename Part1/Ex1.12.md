```
//Dockerfile for frontend
# Base image
FROM node:10

# Create app directory
WORKDIR /usr/src/app

# Copy package.json & package-lock.json
# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY package*.json ./
RUN npm install 

COPY . .

EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD ["npm", "start"]
```

```
//Build the frontend image
~ neeraj$ docker build -t neeraj/frontendexample .
```

```
//Dockerfile for backend
From node:10
WORKDIR /usr/src/app
COPY package.json .
COPY package-lock.json .
RUN npm install
COPY . .
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]
```

```
//Build the backend image
~ neeraj$  docker build -t neeraj/backendexample .
```

```
//Run the frontend image in a container
~ neeraj$ docker run -p 5000:5000 -d neeraj/frontendexample
```

```
//Run the backend image in a container
~ neeraj$ docker run -p 8000:8000 -v $(pwd)/logs.txt:/usr/src/app/logs.txt -d neeraj/backendexample
```
