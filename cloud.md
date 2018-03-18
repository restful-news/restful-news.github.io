---
layout: default
title: Cloud Deployment
---
# Cloud Deployment

## Running on AWS Ubuntu 16.04 AMI
1. Clone repo to `/srv/restful-news` (use `~/.ssh/read-key` & `~/.ssh/config` file)
2. Set environment variables file `.env` (see .env.example)
2. Run `restful-news/scripts/init.sh` to set up server

## Useful commands

- `docker-compose logs` Show logs
- TODO: Route up proper PM2 logs to file

## Environment setup

Environment variables from `.env` are accessible by the Node app through docker-compose.yml which routes them into the api container. PM2 automatically makes them available to each Node server.
