FROM node:20-slim AS base

WORKDIR /app

RUN apt update \
  && apt install wget curl git vim bash-completion -y \
  && apt clean

RUN wget -qO- https://get.pnpm.io/install.sh | ENV="$HOME/.bashrc" SHELL="$(which bash)" bash -

RUN echo 'source /etc/profile.d/bash_completion.sh' >> "$HOME/.bashrc"

EXPOSE 3000