FROM node:18-alpine

RUN mkdir /app

WORKDIR /app

COPY package-lock /app

COPY package.json app

RUN npm install

COPY . app

ENV PORT=10000

CMD ["npm" , "start"]