# Lightweight dev container: Node 18 + Python3 + common tooling
FROM mcr.microsoft.com/devcontainers/base:ubuntu

ARG NODE_VERSION=18

ENV DEBIAN_FRONTEND=noninteractive

# Install common tools, Node.js and Python
RUN apt-get update \
  && apt-get install -y curl python3 python3-pip build-essential git \
  && curl -fsSL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash - \
  && apt-get install -y nodejs \
  && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Ensure code-server user exists (vscode is the default remoteUser used by Codespaces/devcontainers)
USER vscode
WORKDIR /workspace
