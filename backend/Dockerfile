# ベースイメージ（base image）: OpenJDK 21のslim版を使用
# slim版は軽量化されたLinuxディストリビューション
FROM openjdk:21-jdk-slim

# 作業ディレクトリ（working directory）を設定
# コンテナ内でのファイル操作の基準となるディレクトリ
WORKDIR /app

# Gradleラッパー（Gradle wrapper）ファイルをコピー
# Gradleラッパーはプロジェクト固有のGradleバージョンを使用するためのツール
COPY gradlew .
COPY gradle gradle
COPY build.gradle .
COPY settings.gradle .

# gradlewファイルに実行権限を付与
# chmod +x は実行可能（executable）にするコマンド
RUN chmod +x ./gradlew

# ソースコード（source code）をコピー
COPY src src

# Spring Bootアプリケーションをビルド
# bootJarはSpring Bootの実行可能JARファイルを作成するタスク
RUN ./gradlew bootJar

# ポート8080を公開（expose）
# アプリケーションがこのポートでリクエストを受け付けることを宣言
EXPOSE 8080

# コンテナ起動時に実行するコマンド
# JARファイル（Java Archive）を実行してSpring Bootアプリケーションを起動
CMD ["java", "-jar", "build/libs/backend-0.0.1-SNAPSHOT.jar"]