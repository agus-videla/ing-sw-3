FROM node:13.12.0-alpine AS node_build
WORKDIR /app
COPY ./*json ./
RUN npm install
COPY . ./
RUN npm run build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
RUN rm -rf ./* # remove default nginx resources
COPY --from=node_build /app/build .
ENTRYPOINT ["nginx", "-g", "daemon off;"]
