FROM node:alpine

LABEL stage="BUILDING_FRONTEND_APP"

WORKDIR /app

COPY . /app

RUN npm install --global yarn --force
RUN yarn install

CMD [ "npm", "run", "build" ]
