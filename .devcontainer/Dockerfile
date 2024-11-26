FROM node:20-slim AS base

WORKDIR /app

RUN cp /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

RUN apt update \
  && apt dist-upgrade -y \
  && apt install wget curl git vim  \
  bash-completion procps psmisc htop iproute2 -y \
  && apt clean
  
# Oh My Bash
RUN bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)"
RUN sed -i 's/OSH_THEME="font"/OSH_THEME="agnoster"/g' "$HOME/.bashrc"
  
# PNPM
RUN wget -qO- https://get.pnpm.io/install.sh | ENV="$HOME/.bashrc" SHELL="$(which bash)" bash -

# Bash auto completion
RUN echo 'source /etc/profile.d/bash_completion.sh' >> "$HOME/.bashrc"

EXPOSE 3000