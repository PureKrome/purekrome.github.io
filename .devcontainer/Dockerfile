FROM mcr.microsoft.com/devcontainers/javascript-node:1-20-bullseye

# Enable reliable file watching in containerized environments (especially on Windows/macOS hosts)
ENV WATCHPACK_POLLING=true
ENV CHOKIDAR_USEPOLLING=true

# Install specific npm version for reproducible devcontainers
# Install GitHub CLI (gh) via official apt repository
USER root
RUN npm install -g npm@11.11.1 \
    && curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
    && chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
    && apt-get update \
    && apt-get install -y gh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
USER node
