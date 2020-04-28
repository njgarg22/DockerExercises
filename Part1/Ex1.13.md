```
//clone the project
~ neeraj$ git clone https://github.com/docker-hy/spring-example-project.git
```

```
//Dockerfile
FROM openjdk:8
WORKDIR /usr/src/myapp
COPY . .
RUN ./mvnw package
EXPOSE 8080
CMD [ "java", "-jar", "./target/docker-example-1.1.3.jar" ]
```

```
//Build the image
~ neeraj$ docker build -t javaspring .
```

```
//Run the image in a container
~ neeraj$ docker run -p 8080:8080 -d javaspring
```

```
//Check the results in the browser. Click on `press here` button. `Success` will be displayed.
http://localhost:8080/
```
