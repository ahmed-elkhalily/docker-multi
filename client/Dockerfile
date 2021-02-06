FROM node:alpine as builder
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000

COPY ./nginx/defualt.conf /etc/nginx/conf.defualt/defualt.conf
COPY --from=builder /app/build /usr/share/nginx/html