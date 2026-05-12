# BUILD STAGE

FROM node:20 AS build

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

# NGINX STAGE

FROM nginx:alpine

COPY --from=build /app/dist/frontend-angular/browser /usr/share/nginx/html

EXPOSE 80