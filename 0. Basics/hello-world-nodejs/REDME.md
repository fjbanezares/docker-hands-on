## Create js code

Create index.js with following code

This is a simple Node.js application that runs an HTTP server. When you access the server in your web browser, it will return a plain text message with the content "Hello, World!".


```java
const http = require('http');

const hostname = '0.0.0.0';
const port = 8000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

The server will start listening on port 8000.


## Create Dockerfile

Create Dockerfile with following code

```dockerfile
FROM node:12

COPY . .

EXPOSE 8000

CMD ["node", "index.js"]

```

## Build Image
```shell
docker build -t hw .
```

## Run Container
```shell
docker run -p 8000:8000 my-app
```

This will start the container and expose the web server on port 8000. You can access the web server in your web browser at http://localhost:8000.

