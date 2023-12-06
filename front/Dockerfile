FROM node:current-alpine

WORKDIR /app
COPY . /app/

RUN apk update && apk add bash
RUN apk add nginx
RUN npm install
# RUN npm build
RUN mkdir -p /usr/share/nginx/html
COPY ./nginx/default.conf /etc/nginx/http.d/default.conf
RUN cp -r ./html/* /usr/share/nginx/html

EXPOSE 8080

CMD ["nginx", "-g", "pid /tmp/nginx.pid; daemon off;"]