# Node.jsの公式イメージを使用
FROM node:18-alpine

WORKDIR /app

# Yarnをインストール
RUN corepack enable

# 開発モードでNext.jsアプリを実行するためのコマンド
CMD ["sh", "-c", "if [ -f package.json ]; then yarn dev; else yarn create next-app . --typescript --eslint --no-tailwind --app --src-dir --import-alias '@/*' && yarn dev; fi"]
