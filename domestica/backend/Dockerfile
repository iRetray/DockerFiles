FROM rust:1.60-slim-buster

WORKDIR /app

RUN apt update && \
    apt upgrade -y && \
    apt-get install -y libwebkit2gtk-4.0-dev \
    build-essential \
    curl \
    wget \
    libssl-dev \
    libgtk-3-dev \
    libappindicator3-dev \
    librsvg2-dev
