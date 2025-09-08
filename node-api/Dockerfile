FROM node:lts-bullseye
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install --only=dev
COPY . .
ENV PORT=88
EXPOSE 88
CMD [ "node", "index.js" ]