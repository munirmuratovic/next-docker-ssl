# Install dependencies only when needed
FROM node:19-alpine3.15 AS deps
# Check https://github.com/nodejs/docker-node/tree/b4117f9333da4138b03a546ec926ef50a31506c3#nodealpine to understand why libc6-compat might be needed.
RUN apk add --no-cache libc6-compat
WORKDIR /app
COPY package.json pnpm-lock.yaml ./
COPY . .
RUN npm install

RUN npx prisma generate
RUN npm run build

ENV NODE_ENV production

EXPOSE 3000

ENV PORT 3000

CMD ["node_modules/.bin/next", "start"]