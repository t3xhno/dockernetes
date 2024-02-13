FROM node

WORKDIR /app
# This is an optimization, so that the next layer (npm i)
# only runs if something in package.json has changed,
# and doesn't get affected by code changes
COPY package.json .
RUN npm i
COPY . .
EXPOSE 3000

CMD ["node", "server.js"]
