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

### cat /etc/os-release

PRETTY_NAME="Ubuntu 22.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.4 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy

### CPU

13th Gen Intel(R) Core(TM) i7-13700F

### GPU

NVIDIA GeForce RTX 4070 Ti

### mem

32G

### LICENSE

別紙参照
