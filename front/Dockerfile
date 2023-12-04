FROM node:14.17.1-alpine

WORKDIR /app
COPY . /app/

RUN apk update && apk add bash
RUN apk add nginx
RUN npm install
# RUN npm build
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
# RUN mkdir /usr/share/nginx
# RUN cp -r ./build /usr/share/nginx/html

EXPOSE 8080

CMD ["nginx", "-g", "pid /tmp/nginx.pid; daemon off;"]