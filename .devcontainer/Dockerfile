# 基本のイメージ
FROM mcr.microsoft.com/devcontainers/base:jammy

# 環境変数とユーザー設定
ARG DEBIAN_FRONTEND=noninteractive
ARG USER=vscode
ARG CAFEOBJ_VERSION=1.6.1
ENV HOME="/home/$USER"

# 必要なパッケージのインストール
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    ca-certificates \
    git \
    libssl-dev \
    zlib1g-dev \
    libbz2-dev \
    libreadline-dev \
    libsqlite3-dev \
    wget \
    curl \
    llvm \
    libncurses5-dev \
    xz-utils \
    tk-dev \
    libxml2-dev \
    libxmlsec1-dev \
    libffi-dev \
    liblzma-dev \
    sbcl  # SBCL（Common Lisp）を追加

# CafeOBJのソースをクローンし、特定のタグをチェックアウトしてインストール
RUN git clone https://github.com/CafeOBJ/cafeobj.git $HOME/cafeobj && \
    cd $HOME/cafeobj && \
    git checkout tags/v${CAFEOBJ_VERSION} && \
    ./configure --with-lisp=sbcl && \
    make && \
    make install

# 環境変数の設定
ENV PATH="/usr/local/bin:$PATH"
