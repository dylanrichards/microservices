FROM node:18-alpine as source

WORKDIR /app
COPY package*.json ./

# https://docs.npmjs.com/cli/v8/commands/npm-ci
RUN npm ci && npm cache clean --force
COPY . .
RUN npm run build


FROM nginx:stable-alpine
COPY --from=source /app/build /usr/share/nginx/html
COPY nginx/nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
