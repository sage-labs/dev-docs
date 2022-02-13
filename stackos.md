# StackOS Documentation

![StackOS](https://cdn-images-1.medium.com/max/544/1*1U2bGZGGBTjS1qLPuHU_Cg@2x.png)

Documentation around different use cases for using [StackOS](https://www.home.stackos.io/)

## Getting Started with Docker

![Docker](https://d1.awsstatic.com/acs/characters/Logos/Docker-Logo_Horizontel_279x131.b8a5c41e56b77706656d61080f6a0217a3ba356d.png)

### Docker Account

Create an account with [Dockerhub](https://hub.docker.com/) so you can push your Docker containers.

### Install Docker on your CLI

Follow this [link](https://docs.docker.com/engine/install/ubuntu/) to install the docker cli on your terminal.

Verify you have it installed by running `docker` in the terminal and verify you have an output.

### Docker Login

To be able to do a `docker push` you need to ensure you are logged in.

Run a `docker login` in your terminal to log into your DockerHub Account.

### Docker Build

Once you create your Dockerfile for packaging your application you will need to build the container.

1. `cd` into the directory your **Dockerfile** exists
2. Run `docker build .` which looks for a **Dockerfile** in the current directory and builds it.


### Docker Tag

After the docker build succeeds, you will now need to tag your container.

1. Run `docker images` to get the Short SHA of your container, it should look something like this: `9eb518b1dfbc`.
2. Once you retrieve your Short SHA, run `docker tag <SHORT_SHA> <DOCKER_USERNAME>/<DOCKER_REGISTRY_NAME>:<SHORT_SHA>`.
  * Example: `docker tag 9eb518b1dfbc sagelabs/test-image:9eb518b1dfbc`
4. Finally, do a Docker push. `<DOCKER_USERNAME>/<DOCKER_REGISTRY_NAME>:<SHORT_SHA>`
  * Example:`docker push sagelabs/test-image:9eb518b1dfbc`

## Getting Started with StackOS

### Add BSC/StackOS to your Metamask wallet

[Follow this guide](https://myterablock.medium.com/how-to-add-binance-smart-chain-network-to-metamask-and-connect-it-to-pancakeswap-c4a245a2952d) to add BSC to your Metamask wallet if it is not already there.

Then switch over to Smart Chain in Metamask and add Stack token.

[Use coingecko](https://www.coingecko.com/en/coins/stackos) to get the proper contract to add, it should auto populate in metamask.

### Purchase $Stack tokens on Pancake swap

[Follow this guide](https://medium.com/stackos/how-to-buy-stack-on-pancakeswap-using-metamask-3e122dc04061) to purchase $Stack tokens.

### Log into Stack OS

[Use this link](https://app.stackos.io/) to log into StackOS.

Depending on the needs for availability, chose the network, and then chose the cluster you want to deploy your application onto.

### Add $Stack tokens to cluster

Once logged in you should click the `Upgrade` tab.

From there you will be able to pruchase the CPU / Memory / Storage needed.

After filling in what you want to purchase, click the `Upgrade` Button on the bottom left.

You are now ready to deploy your application.
