FROM node:14-alpine
RUN apk add --no-cache git
RUN git clone https://github.com/kkenan/basic-microservices.git
WORKDIR /app/node-app
RUN npm install
EXPOSE 3000
CMD ["npm", "start"]