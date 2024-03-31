# Use the official Ubuntu 22.04 LTS as a parent image
FROM ubuntu:22.04

# Install basic packages
RUN apt-get update && apt-get install -y \
    curl \
    wget \
    git \
    vim \
    nano \
    unzip \
    zip \
    python3 \
    python3-pip \
    python3-venv \
    python3-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Install Node.js (Latest Version)
# The setup script will automatically install the latest stable version of Node.js
RUN curl -fsSL https://deb.nodesource.com/setup_current.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && rm -rf /var/lib/apt/lists/*

# Verify Node.js and npm installation
RUN node -v
RUN npm -v

# Optional: If you need to compile and install native addons from npm, also install build tools
RUN apt-get update && apt-get install -y gcc g++ make

# Clean up the apt cache to reduce image size
RUN rm -rf /var/lib/apt/lists/*
