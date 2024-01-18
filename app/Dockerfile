# Stage 1 - Build the Vite Vue App
FROM node:14 AS builder

WORKDIR /app

COPY app/package*.json ./
RUN npm install

COPY app .
RUN npm run build

# Stage 2 - Create the final image with Nginx
FROM nginx:alpine

COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]