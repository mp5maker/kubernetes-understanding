FROM node:14.18.0

WORKDIR /usr/src/app

COPY package*.json ./
RUN yarn install
COPY . .

CMD ["yarn", "start"]
