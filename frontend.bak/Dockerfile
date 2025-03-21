FROM node:18 AS builder
WORKDIR /app
COPY angular-app/ .
RUN npm install && npm run build --prod

FROM nginx:alpine
COPY --from=builder /app/dist/angular-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;
