# docker_memo_to_self

https://github.com/miolab/docker_memo_to_self.git

## Docker チートシート

### 環境 / バージョン確認

- Mac

  - Docker Desktop for Mac

    ```
    $ docker -v
    Docker version 19.03.8, ...
    ```

* Win (10 pro)

  - Docker Toolbox

    - Hyper-V 抜き + Docker Quickstart Terminal

    ```
    $ docker -v
    Docker version 18.03.0-ce, ...
    ```

### Docker Desktop for Mac のインストール

```
$ brew install docker

$ brew cask install docker

$ open /Applications/Docker.app
```

- `brew cask install` がうまく通らない場合は、  
  `brew update-reset && brew update` で一度アップデートしなおす。

---

## Docker Image

- コンテナ実行に必要なファイルをまとめたもの（= ファイルシステム）。

- `$ docker run image_hoge` とかで DockerHub から取ってくる。

  - すでにイメージ持ってたら即実行。DockerHub を見に行くプロセスは省略される。

### `$ docker run`

以下コマンドをまとめて実行したもの。

- docker pull イメージの取得
- docker create コンテナの作成
- docker start コンテナの起動

### `$ docker images`

image の一覧を取得して表示。

### `$ docker inspect hoge_image_name`

詳細情報を表示。

### `$ docker rmi hoge_image_name`

image を削除。

- 強制削除するなら、`rmi -f`

---

### **prune** コマンド

- 停止中の全コンテナ削除

  ```
  $ docker container prune

  WARNING! This will remove all stopped containers.
  Are you sure you want to continue? [y/N] y

  Deleted Containers:
  .
  .
  .
  Total reclaimed space: 2.081GB

  ```

- タグ付けなし＆コンテナから参照されてない Image 全削除

  ```
  $ docker image prune

  WARNING! This will remove all dangling images.
  Are you sure you want to continue? [y/N]

  Deleted Images:
  .
  .
  Total reclaimed space: 18.75GB
  ```
