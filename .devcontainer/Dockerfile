FROM mcr.microsoft.com/devcontainers/javascript-node:1-20-bullseye

# Enable reliable file watching in containerized environments (especially on Windows/macOS hosts)
ENV WATCHPACK_POLLING=true
ENV CHOKIDAR_USEPOLLING=true

# Install specific npm version for reproducible devcontainers
USER root
RUN npm install -g npm@11.11.1
USER node
