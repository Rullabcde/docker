FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json .
RUn npm install

COPY . .
RUN npm run build

FROM nginx:alpine

COPY --from=builder /app/build /usr/share/nginx/html

EXPOSE 80