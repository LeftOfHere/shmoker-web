FROM --platform=amd64 node:17 as build
COPY ./ /app

WORKDIR /app
RUN yarn install 

RUN yarn build

FROM --platform=amd64 nginx:alpine
RUN mkdir /app
COPY --from=build /app/dist /app
COPY .docker/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
ENTRYPOINT ["nginx", "-g", "daemon off;"]
