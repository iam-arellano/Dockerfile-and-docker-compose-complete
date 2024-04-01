FROM node:20-alpine

# set default dir so that next commands executes in /usr/src/app dir
WORKDIR /usr/src/app


COPY app .

# will execute npm install in /usr/src/app because of WORKDIR
RUN npm install

# no need for /usr/src/app/server.js because of WORKDIR
CMD ["node", "server.js"]
