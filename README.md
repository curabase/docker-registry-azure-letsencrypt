# Purpose

This repo makes it easy to setup a secure docker registry with encryption and 
user authentication on Azure. It uses a `docker-compose.yml` file and shell
script to automate most of it away.

# Requirements

  1. You will want to have a domain pointed at the IP of your VM.
  1. You will want to make sure ports 80, 443, and 5000 are open to the VM.

# Installation

  1. Setup a new VM (Ubuntu 16.04)
  1. Clone this repo `git clone https://github.com/undernewmanagement/docker-registry-letsencrypt-azure`
  1. `cd docker-registry-letsencrypt-azure`
  1. (optional) - If docker is not already installed, you can use the `setup-docker-ubuntu-16.04-xenial.sh`
     script to install the latest version.
  1. configure you environment variable using `evn.example` as a template. Save it as `.env`.  You will want
to fill our your Azure storage credentials.
  1. setup your TLS certs with Letsencrypt `docker-compose -f letsencrypt.yml up`
  1. start the docker registry with `docker-compose -f docker-compose.yml up -d`
  1. create your first registry user with `docker run --entrypoint htpasswd registry:2 -Bbn {user} {password} > data/auth/htpasswd`

# Using the registery

Once installed and configured, you will have docker registry up and running on port 5000.

You should be able to login with `docker login -u <user> -p <passwrd> <host>:5000


# License

MIT License


