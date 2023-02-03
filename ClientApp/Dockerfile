FROM node:19-alpine as build

WORKDIR /app
COPY package.json .
COPY package-lock.json .

RUN npm install

COPY . .
RUN npm run build

FROM nginx:1.21-alpine
COPY --from=build /app/dist /usr/share/nginx/html

