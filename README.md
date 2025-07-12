# プロジェクト起動手順

このプロジェクトは以下の構成で動作します：
- **Backend**: Spring Boot (ポート: 8080)
- **Frontend**: Next.js (ポート: 3000)
- **Database**: PostgreSQL (ポート: 5432)

## 前提条件

- Docker
- Docker Compose

## 起動方法

### 1. 全サービスを一括起動

```bash
docker-compose up -d
```

### 2. ログを確認

```bash
docker-compose logs -f
```

### 3. 個別サービスの起動

```bash
# データベースのみ
docker-compose up -d database

# バックエンドのみ（データベース必須）
docker-compose up -d database backend

# フロントエンドのみ（バックエンド必須）
docker-compose up -d database backend frontend
```

## アクセス先

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:8080
- **Database**: localhost:5432
  - データベース名: `backend_db`
  - ユーザー名: `backend_user`
  - パスワード: `backend_password`

## 停止方法

```bash
# 全サービス停止
docker-compose down

# データも削除する場合
docker-compose down -v
```

## 開発時のコマンド

```bash
# コンテナの再ビルド
docker-compose up --build

# 特定サービスの再ビルド
docker-compose up --build backend
docker-compose up --build frontend

# コンテナ内のログ確認
docker-compose logs backend
docker-compose logs frontend
docker-compose logs database
```