FROM node:alpine as build

WORKDIR /app

COPY frontend/package.json ./
RUN npm install
COPY frontend/src ./src
COPY frontend/public ./public

RUN npm run build

FROM nginx:alpine
EXPOSE 80
COPY --from=0 /app/build /usr/share/nginx/html