FROM node:16-alpine

WORKDIR /app

COPY package*.json ./

RUN npm ci

RUN mkdir node_modules/.cache && chmod -R 777 node_modules/.cache

COPY . /app

EXPOSE 3000

CMD [ "npm", "run", "start" ]