FROM node:18-alpine

WORKDIR /app

COPY package.json pnpm-lock.yaml pnpm-workspace.yaml ./

RUN npm install -g pnpm

COPY . .

RUN pnpm install
WORKDIR /app/packages/auth
RUN pnpm build

ENV PORT=3000
EXPOSE 3000
CMD ["node", "dist/main.js"]

