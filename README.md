# docker-wine

## 概要

docker上で、wineを使用して、windowsアプリケーション（GUI含）を実行する。

## 起動方法

docker-compose up --build

## ログイン

docker exec -it c_wine bash

## 停止方法

docker-compose down

## 注意事項

・".bashrc"に、以下コマンドを埋め込み済み（ウィンドウ描画）

xhost +local:

・windowsのCドライブは以下に配置

/root/.wine/drive_c

・".env"ファイル中に、コンテナ中のディレクトリに関するパス指定あり。

__DOCKER_ROOT=/mnt/sda2_f/10_ubuntu/E0_docker


## 動作確認環境

### OS

Ubuntu 22.04.4 LTS

### CPU

13th Gen Intel(R) Core(TM) i7-13700F

### GPU

NVIDIA GeForce RTX 4070 Ti

### mem

32G

### LICENSE

別紙参照
