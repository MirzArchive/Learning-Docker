FROM node:alpine3.17

RUN addgroup app && adduser -S -G app app

USER app

WORKDIR /app

RUN mkdir data

COPY --chown=app:node package*.json .

RUN npm install

COPY --chown=app:node . .

EXPOSE 3000

ENTRYPOINT [ "npm", "run", "dev" ]