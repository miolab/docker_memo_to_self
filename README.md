# docker_memo_to_self

https://github.com/miolab/docker_memo_to_self.git

## Docker チートシート

* 自分用メモ。
* Docker雰囲気で使ってる感があったので、整理も兼ねて。

### 環境

- Win10 pro
- Docker Toolbox
  - Hyper-V抜き + Docker Quickstart Terminal  
    (現WinPCではDocker Windowsでは重かったため)

### バージョン確認

```
$ docker -v

Docker version 18.03.0-ce, ...
```

---

## Docker Image

- コンテナ実行に必要なファイルをまとめたもの（= ファイルシステム）。
- `$ docker run image_hoge` とかでDockerHubから取ってくる。
  - すでにイメージ持ってたら即実行。DockerHubを見に行くプロセスは省略される。

### `$ docker run`

以下コマンドをまとめて実行したもの。

- docker pull    イメージの取得
- docker create  コンテナの作成
- docker start   コンテナの起動

### `$ docker images`

imageの一覧を取得して表示。

### `$ docker rmi hoge_image_name`

imageを削除。

- 強制削除するなら、`rmi -f`

