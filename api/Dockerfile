FROM node:14

WORKDIR /app

COPY api/package*.json ./
RUN npm install

COPY api .

CMD ["pm2-runtime", "app.js"]