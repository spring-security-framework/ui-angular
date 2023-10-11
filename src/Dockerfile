FROM node:14-alpine AS build
WORKDIR /usr/src/app
COPY . .
RUN npm install

RUN npm run build

FROM nginx:1.23.2-alpine
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY --from=build /usr/src/app/dist/bank-app-ui /usr/share/nginx/html
