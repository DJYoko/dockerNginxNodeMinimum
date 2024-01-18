# ベースイメージの指定
FROM nginx

# 必要なツールやパッケージのインストール
RUN apt-get update && apt-get install -y \
    curl \
    nodejs \
    npm

# Nginxのデフォルト設定を削除
RUN rm /etc/nginx/conf.d/default.conf

# カスタムNginx設定ファイルのコピー
COPY docker/nginx.conf /etc/nginx/conf.d/

# コンテナ内の作業ディレクトリの指定
WORKDIR /usr/share/nginx/html

# アプリケーションのソースコードをコピー
COPY . .

# npm install の実行
# RUN npm install

# ポートのエクスポート
EXPOSE 80

# Nginxをフォアグラウンドで実行
CMD ["nginx", "-g", "daemon off;"]
