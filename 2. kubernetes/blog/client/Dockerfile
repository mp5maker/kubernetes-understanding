FROM node:14.18.0

ENV CI=true
ENV WDS_SOCKET_PORT=0

WORKDIR /usr/src/app

COPY package*.json ./
RUN yarn install
COPY . .

CMD ["yarn", "start"]
