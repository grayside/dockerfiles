# Serverless

Wraps up the serverless framework to go.

## Example docker-compose.yml

This example has a focus on Google Cloud provider.

```
version: '3.5'

x-base: &base
  volumes:
    - .:/app
    - /data/triviality/cache:/cache
    - ~/.gcloud/${TRIVIALITY_KEY:-triviality-keyfile}.json:/root/.gcloud/keyfile.json
    - ~/.config/gcloud:/root/.config/gcloud
  working_dir: /app
  network_mode: bridge

services:
  serverless:
    <<: *base
    build: .
    entrypoint: ["serverless"]
    environment:
      - SLS_DEBUG

  yarn:
    <<: *base
    build: .
    entrypoint: ["yarn"]

  cli:
    <<: *base
    build: .
    entrypoint: ["/usr/bin/env", "ash", "--login"]
    environment:
      GCP_PROJECT_ID

  gcloud:
    <<: *base
    image: lakoo/node-alpine-gcloud
    entrypoint: ["gcloud"]
    command: ["help"]
    environment:
      CLOUDSDK_CORE_PROJECT
```
