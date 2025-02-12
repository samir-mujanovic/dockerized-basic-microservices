FROM node:9.11.2-alpine
RUN apk update && \
    apk add --no-cache git
RUN git clone https://github.com/kkenan/basic-microservices.git /app
WORKDIR /app/node-app
RUN npm install

EXPOSE 8081
CMD ["node", "index.js"]