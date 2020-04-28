```
//clone the project
~ neeraj$ git clone https://github.com/docker-hy/rails-example-project.git
```

```
//Dockerfile
FROM ruby:2.6.0
WORKDIR /usr/src/app
RUN apt-get update && apt-get install sudo -y
RUN apt-get update && sudo apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
RUN sudo apt-get install -y nodejs
COPY Gemfile Gemfile.lock ./
RUN bundle install
COPY . .
RUN rails db:migrate
EXPOSE 3000
CMD ["rails", "s"]
```

```
//Build the image
~ neeraj$ docker build -t ruby .
```

```
//Run the image in a container
~ neeraj$ docker run -p 3000:3000 -d ruby
```

```
//Check the results in the browser. Click on `press` button. `Press was successfully created` is displayed.
http://localhost:3000/
```
