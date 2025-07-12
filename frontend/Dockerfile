# ベースイメージ: Node.js 20のAlpine Linux版を使用
# Alpine Linuxは軽量で安全性の高いLinuxディストリビューション
FROM node:20-alpine

# 作業ディレクトリを設定
# コンテナ内でのファイル操作の基準となるディレクトリ
WORKDIR /app

# package.jsonとpackage-lock.jsonをコピー
# 依存関係（dependencies）の情報が含まれるファイル
COPY package*.json ./

# 依存関係をインストール
# npm ci は本番環境向けの高速で信頼性の高いインストール方法
RUN npm ci

# アプリケーションのソースコードをコピー
COPY . .

# Next.jsアプリケーションをビルド
# 本番環境向けに最適化されたファイルを生成
RUN npm run build

# ポート3000を公開
# Next.jsアプリケーションがこのポートでHTTPリクエストを受け付ける
EXPOSE 3000

# コンテナ起動時に実行するコマンド
# npm start でNext.jsの本番サーバーを起動
CMD ["npm", "start"]