From node:13.13.0 as client

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

COPY package.json /usr/src/app

# RUN npm cache clean

RUN npm install

COPY . /usr/src/app

# RUN yarn build

FROM nginx:latest

EXPOSE 80

# Copy all the contents from the build directory into the web root
COPY --from=client /usr/src/app/build/ /var/www/html

COPY ./nginx/default.conf /etc/nginx/conf.d

CMD ["nginx", "-g", "daemon off;"]