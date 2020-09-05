FROM node:13.13.0-alpine

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json /usr/src/app

# RUN npm cache clean

RUN npm install

COPY . /usr/src/app
EXPOSE 3002
CMD ["npm","start"]

