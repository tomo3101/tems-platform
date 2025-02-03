FROM node:22-alpine AS base

# The web Dockerfile is copy-pasted into our main docs at /docs/handbook/deploying-with-docker.
# Make sure you update this Dockerfile, the Dockerfile in the web workspace and copy that over to Dockerfile in the docs.

# Enable pnpm
ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"
RUN corepack enable

# Install Git and SSH
RUN apk update
RUN apk add --no-cache git openssh

# Clone the repository
WORKDIR /workspace
COPY .gitconfig /root
RUN git clone https://github.com/tomo3101/train-event-manage-system.git
