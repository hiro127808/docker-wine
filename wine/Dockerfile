FROM ubuntu:latest
ENV DEBIAN_FRONTEND=noninteractive
ENV LC_ALL=ja_JP.utf8
ENV LANG=ja_JP.UTF-8
ENV LANGUAGE="ja_JP:ja"

RUN dpkg --add-architecture i386

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y \
    git \
    curl \
    wget \
    tar \
    unzip \
    zip \
    && echo "" > /dev/null

RUN apt-get install -y \
    wine \
    winetricks \
    && echo "" > /dev/null

RUN apt-get install -y \
    libc6:i386 \
    # libncurses5:i386 \
    libstdc++6:i386 \
    zlib1g:i386 \
    && echo "" > /dev/null

RUN winetricks fonts allfonts
RUN winetricks cjkfonts

RUN apt install -y \
    language-pack-ja-base \
    language-pack-ja \
    ibus-mozc \
    && echo "" > /dev/null
    
RUN sed -i 's/^#ja_JP.UTF-8 UTF-8/ja_JP.UTF-8 UTF-8/' /etc/locale.gen

RUN locale-gen
RUN echo LANG=ja_JP.UTF-8 > ~/.bashrc

# WORKDIR /tmp
# RUN wget https://ja.osdn.net/projects/ume-font/downloads/22212/umefont_670.tar.xz
# RUN tar Jxfv umefont_670.tar.xz
# RUN rm umefont_670.tar.xz
# RUN mv umefont_670 /usr/share/fonts/truetype/

RUN mkdir NotoSansCJKjp
WORKDIR /tmp/NotoSansCJKjp
RUN wget https://noto-website-2.storage.googleapis.com/pkgs/NotoSansCJKjp-hinted.zip
RUN unzip NotoSansCJKjp-hinted.zip
RUN rm NotoSansCJKjp-hinted.zip
WORKDIR /tmp
RUN mv NotoSansCJKjp /usr/share/fonts/opentype/

# NotoSerifCJKjp-hinted.zipのダウンロード
RUN mkdir NotoSerifCJKjp
WORKDIR /tmp/NotoSerifCJKjp
RUN wget https://noto-website-2.storage.googleapis.com/pkgs/NotoSerifCJKjp-hinted.zip
RUN unzip NotoSerifCJKjp-hinted.zip
RUN rm NotoSerifCJKjp-hinted.zip
WORKDIR /tmp
RUN mv NotoSerifCJKjp /usr/share/fonts/opentype/

COPY ./wine-japanese.reg /tmp/.
RUN regedit wine-japanese.reg
COPY ./EntryPoint.sh /tmp/.

WORKDIR /tmp
RUN ln -s /root/.wine/drive_c/ /drive_c
RUN ln -s "/root/.wine/drive_c/Program Files (x86)" /program_file
# unzip -O CP932 hoge.zip

