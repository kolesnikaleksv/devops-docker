# FROM node:20-alpine
ARG NODE_VERSION=22.18.0

FROM node:${NODE_VERSION}-alpine

RUN addgroup app && adduser -S -G app app

USER app

WORKDIR /app

COPY package*.json ./

USER root

RUN chown -R app:app .

USER app

RUN npm install

COPY . .

EXPOSE 5173

CMD ["npm", "run", "dev"]

# comand for building image
# docker build -t react-docker .
# comand for runing project in dev
# docker run -p 5173:5173 -v "${PWD}:/app" -v /app/node_modules react-docker
# In this case we use command for compose.yaml file : docker compose up
