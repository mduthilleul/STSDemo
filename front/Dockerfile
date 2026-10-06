FROM node:24 AS build

WORKDIR /app

COPY . .

RUN npm install
RUN npm run build

FROM caddy:alpine

WORKDIR /var/www/html
COPY --from=build /app/dist .
COPY conf/Caddyfile /etc/caddy/Caddyfile



