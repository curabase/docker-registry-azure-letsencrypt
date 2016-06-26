# Purpose

This repo makes it easy to setup a secure docker registry with encryption and 
user authentication on Azure. It uses a `docker-compose.yml` file and shell
script to automate most of it away.

# Requirements

  1. You will want to have a domain pointed at

# Installation

  1. Setup a new VM with docker. I prefer to use the Ubuntu image with the docker extention.
  1. Once the machine is up you will want to point a domain at its IP address.
  1. Clone this repo `git clone https://github.com/undernewmanagement/docker-registry-letsencrypt-azure`
  1. `cd docker-registry-letsencrypt-azure`
  1. `./setup-lets-encrypt.sh` - this will run letsencrypt and download the certificates
  1. 
