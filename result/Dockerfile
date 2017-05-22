#FROM node:5.11.0-slim - cannot find -slim
FROM node:5.11.0

WORKDIR /app

#remove nodemon, only required for development, not runtime - had trouble fining all associated packages
#change corresponding command in docker-compose file to just node
#RUN npm install -g nodemon

ADD package.json /app/package.json

#add proxy config
RUN npm config set proxy http://proxy.am2.hpelabs.net:8080
RUN npm config set https-proxy http://proxy.am2.hpelabs.net:8080 

RUN npm config set registry http://registry.npmjs.org
RUN npm install && npm ls
RUN mv /app/node_modules /node_modules

ADD . /app

ENV PORT 80
EXPOSE 80

CMD ["node", "server.js"]
