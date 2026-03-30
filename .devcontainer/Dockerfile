FROM mcr.microsoft.com/devcontainers/base:ubuntu

# Install required tools
RUN apt-get update && \
    apt-get install -y curl zip unzip && \
    rm -rf /var/lib/apt/lists/*

# Install SDKMAN and Java/Maven as the vscode user
USER vscode
ENV SDKMAN_DIR="/home/vscode/.sdkman"
RUN curl -s "https://get.sdkman.io" | bash && \
    bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh && yes | sdk install java 21.0.3-tem && yes | sdk install maven"

# Add Java and Maven to PATH
ENV PATH="/home/vscode/.sdkman/candidates/java/current/bin:/home/vscode/.sdkman/candidates/maven/current/bin:$PATH"