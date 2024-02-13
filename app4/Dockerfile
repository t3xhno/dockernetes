FROM node:14

WORKDIR /app
COPY package.json .
RUN npm i
COPY . .

# This keeps the node_modules from being overwritten
# when we bind our external source directory to /app
VOLUME [ "/app/node_modules" ]

ENV PORT 80
EXPOSE $PORT

CMD [ "npm", "start" ]
