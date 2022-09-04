FROM node:16-alpine

COPY state /state
WORKDIR /state
RUN npm install

CMD ["npm","run","start"]