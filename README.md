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

to test locally: `eb local run -v`

to deploy: `eb deploy`

## Helpful links:
* https://www.conjur.org
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker-eblocal.html


   ```
