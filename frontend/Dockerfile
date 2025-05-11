# Node.jsの公式イメージを使用
FROM node:18-alpine

WORKDIR /app

# Yarnをインストール
RUN corepack enable && corepack prepare yarn@4.7.0 --activate

ENV YARN_NODE_LINKER=node-modules

COPY . .

RUN yarn install

# 開発モードでNext.jsアプリを実行するためのコマンド
CMD ["yarn", "dev"]
