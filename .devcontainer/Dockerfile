# Use the official Jekyll devcontainer image as the base image
FROM mcr.microsoft.com/devcontainers/jekyll:2-bullseye

# Install additional dependencies
RUN apt-get update && apt-get install -y \
      default-jre \
      wget \
      graphviz \
    && rm -rf /var/lib/apt/lists/*

# Install PlantUML from source
RUN mkdir -p /opt/plantuml \
    && wget https://github.com/plantuml/plantuml/releases/latest/download/plantuml.jar -O /opt/plantuml/plantuml.jar \
    && chmod +x /opt/plantuml/plantuml.jar \
    && echo '#!/bin/bash\njava -jar /opt/plantuml/plantuml.jar "$@"' > /usr/bin/plantuml \
    && chmod +x /usr/bin/plantuml

ENV GRAPHVIZ_DOT=/usr/bin/dot
