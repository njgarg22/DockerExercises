Github repo: https://github.com/njgarg22/SimpleNodeApp

# Description

This is a simple Node.js app that starts a server and listens on port `4000` for connections.
It responds with “Hello World!” for `get` requests to the root URL (/).

## Pull the image

  ```
  docker pull njgarg22/simplenodeapp
  ```

## Run the image

  ```
  docker run -p 4000:4000 -d njgarg22/simplenodeapp
  ```

## Check if it's working correctly

  ```
  Open http://localhost:4000/ in browser. You should be able to see the "Hello World!" message on your screen.
  ```
