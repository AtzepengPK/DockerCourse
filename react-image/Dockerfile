FROM node:alpine as build

WORKDIR /app

COPY frontend/package.json .
RUN npm install
COPY frontend/src ./src
COPY frontend/public ./public

RUN npm run build

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
