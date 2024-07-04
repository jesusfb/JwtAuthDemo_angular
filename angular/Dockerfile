FROM node:alpine AS build
WORKDIR /app

COPY . .
#RUN npm install
#RUN npm run build
RUN npm run build -- --output-path=/dist

# Serve Application using Nginx Server
FROM nginx:alpine
COPY --from=build /app/dist/project-name/ /usr/share/nginx/html
EXPOSE 80
