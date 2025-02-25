# TEMS Platform

## 概要
[Train model Event Management System(TEMS)](https://github.com/tomo3101/tems)のプラットフォームレポジトリです。

## ファイル構成
```
.
├── README.md
├── docker-compose.yml
├── docker-compose-dev.yml
├── mysql
│   ├── Dockerfile                      # MySQLのコンテナのDockerfile
│   └── my.cnf                          # MySQLの設定ファイル
└── node
    ├── Dockerfile                  # Node.jsの開発用コンテナのDockerfile
    └── projects                    # プロジェクトレポジトリ格納用ディレクトリ
```

## .envの設定
Dockerコンテナビルド時に.envにMySQLとPHPMyAdmin用の設定をする必要がある。<br>
以下のコマンドから.env.sampleをコピーして、適宜内容を編集する。
```bash
cp .env.sample .env
```

### .envの設定項目
```
ROOT_PASS=root          # MySQLのrootユーザーのパスワード
DB_NAME=tems-db         # MySQLのデータベース名
DB_USER=tems            # MySQLに追加するユーザー名
DB_PASS=tems            # MySQLに追加するユーザーのパスワード
PMA_USER=tems           # PHPMyAdminのユーザー名
PMA_PASSWORD=tems       # PHPMyAdminのパスワード
```

## 開発環境構築手順

**1. プラットフォームレポジトリをクローン**<br>
開発環境のdocker-compose-dev.ymlを含むレポジトリをクローンします。
```bash
git clone https://github.com/tomo3101/tems-platform.git
```

**2. VSCode Dev Containerを開く**<br>
VSCodeを開き、ウィンドウ左下の `><` のようなボタンをクリックする。<br>
**コンテナーで再度開く**を選択すると、Dev Containerがビルドされる。

※VSCodeの拡張機能で「Dev Container」が必要。また、Dockerを起動しておく必要がある。
