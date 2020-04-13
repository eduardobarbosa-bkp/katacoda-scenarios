Dockerizing a node application

```cat <<EOF > package.json
{
  "name": "docker_web_app",
  "version": "1.0.0",
  "description": "Node.js on Docker",
  "author": "First Last <first.last@example.com>",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.16.1"
  }
}
EOF```{{execute}}


```cat <<EOF > server.js
'use strict';

const express = require('express');

// Constants
const PORT = 8080;
const HOST = '0.0.0.0';

// App
const app = express();
app.get('/', (req, res) => {
  res.send('Learn from a Watopia Containers');
});

app.listen(PORT, HOST);
console.log(`Running on http://${HOST}:${PORT}`);
EOF```{{execute}}


```cat <<EOF > Dockerfile
FROM node:alpine

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
# where available (npm@5+)
COPY package*.json ./

RUN npm install
# If you are building your code for production
# RUN npm ci --only=production

# Bundle app source
COPY . .

EXPOSE 8080
CMD [ "node", "server.js" ]
EOF```{{execute}}


Build a image using Dockerfile

`docker build -t zwift-node .'`{{execute}}

`docker run -it -p 8081:800 -d zwift-node`{{execute}}

`curl localhost:8081`{{execute}}