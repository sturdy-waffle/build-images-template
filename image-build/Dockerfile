FROM ubuntu:focal

# Install curl
RUN apt-get update && apt-get install -y curl

# Install Dependencies Repo
RUN curl -1sLf \
  "https://dl.cloudsmith.io/<TOKEN>/sturdy-waffle/deb-dependencies/cfg/setup/bash.deb.sh" \
  | bash

# Add Security Repository
COPY resources/*.list /etc/apt/sources.list.d/

# Remove Default Repositories
RUN rm /etc/apt/sources.list

# Upgrade system
RUN apt-get update && apt-get upgrade -y
