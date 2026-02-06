FROM node:20 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install --legacy-peer-deps
COPY . .

ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build --prod --legacy-peer-deps

FROM nginx:alpine
COPY --from=build /app/dist/kanban-ui /usr/share/nginx/html
EXPOSE 80
