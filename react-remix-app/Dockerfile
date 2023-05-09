FROM node:20.1.0-alpine3.17

# RUN addgroup app && adduser -S -G app app
# USER app
# WORKDIR /app

# COPY . .
# RUN npm install

# ENV DB_USERNAME=root
# EXPOSE 3000

# ENTRYPOINT [ "npm", "run", "dev" ]

RUN addgroup app && adduser -S -G app app

USER app

WORKDIR /app

COPY --chown=app:node package*.json ./

RUN npm install

COPY --chown=app:node . .

EXPOSE 3000

ENTRYPOINT [ "npm", "run", "dev" ]
