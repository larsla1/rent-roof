FROM node:12-alpine as base

ENV NODE_PATH=src/

RUN mkdir /src
WORKDIR /src

COPY package.json yarn.lock ./
RUN yarn

FROM base as development

COPY . .

CMD ["yarn", "dev"]


FROM development as production

RUN yarn build

CMD ["yarn", "start"]
