# build
FROM node:lts-alpine AS build
WORKDIR /app
COPY package*.json ./
# si tu as un package-lock.json, préfère: RUN npm ci
RUN npm install
COPY . .
RUN npm run build

# runtime
FROM nginx:stable-alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
