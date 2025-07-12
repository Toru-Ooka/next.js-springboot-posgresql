# ベースイメージ: PostgreSQL 15のAlpine Linux版を使用
# PostgreSQLはオープンソースのリレーショナルデータベース管理システム
FROM postgres:15-alpine

# 環境変数（environment variables）を設定
# PostgreSQLデータベースの初期設定情報
ENV POSTGRES_DB=backend_db
ENV POSTGRES_USER=backend_user
ENV POSTGRES_PASSWORD=backend_password

# 初期化SQLスクリプトをコピー
# /docker-entrypoint-initdb.d/ にあるファイルはコンテナ起動時に自動実行される
COPY init.sql /docker-entrypoint-initdb.d/

# ポート5432を公開
# PostgreSQLの標準ポート番号
EXPOSE 5432