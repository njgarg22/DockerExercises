```
//300MB size for frontend image
~ neeraj$ cat Dockerfile 
# Base image
FROM node:10-alpine

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
//117MB size for backend image
~ neeraj$ cat Dockerfile 
From node:10-alpine
WORKDIR /usr/src/app
COPY package.json .
COPY package-lock.json .
RUN npm install
COPY . .
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]
```
