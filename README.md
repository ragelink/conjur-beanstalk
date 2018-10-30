# Welcome to conjur-beanstalk

The beanstalk deployment template for conjur... in this repo we  hope to provide a quick way to drop in and deploy [Get Conjur](https://www.conjur.org/get-started/install-conjur.html) into a beanstalk multi docker container... this repo is a work in progress so expect updates.

## Steps to get setup

Get an AWS account and setup the beanstalk client
[Link to AWS docs](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html) or use our prebuilt beanstalk cli (in a docker container).
#### Using the Amazon EB CLI in Docker

1. Run `bin/build-eb-image`

   This will install Elastic Beanstalk's CLI in a clean Python environment and
   tag it as `amazon-eb-cli`
2. To use it:
   
   ```sh-session
   $ docker run --rm -it amazon-eb-cli -h
   usage: eb (sub-commands ...) [options ...] {arguments ...}
   
   Welcome to the Elastic Beanstalk Command Line Interface (EB CLI). 
   For more information on a specific command, type "eb {cmd} --help".

#### Clone this repo and initialize beanstalk

run `eb init` into the console to initialize your application/environment do this in the folder where you have cloned the repo

there are 2 files that you can use depending on the topology of your deployment: Single instance or MultiInstance

```MultiHost-RDS-Dockerrun.aws.json	
   SingleInstance-Dockerrun.aws.json```

Rename the one you want to Dockerrun.aws.json then test or deploy.

to test locally: `eb local run -v`

to deploy: `eb deploy`

The difference between the two is basically whether you have a small deployment and a single instance of everything will do (pick SingleInstance-Dockerrun.aws.json), however if you want to scale out your environment in an N+1 fashion you can scale out the client/server component and drop the DB inside an RDS configuration and that will scale the DB vertically and then the app tier horizontally. This is probably an easier faster stop gap to deploying the clustered configuration which you may need for extremely highly available environments.

## Helpful links:
* https://www.conjur.org
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker-eblocal.html


   ```
