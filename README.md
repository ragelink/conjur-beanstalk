### conjur-beanstalk

Welcome to the beanstalk module for conjur.

in this repo we  hope to provide a quick way to drop in and deploy conjur https://www.conjur.org/get-started/install-conjur.html into a beanstalk multi docker container... more to come.

### Steps to get setup

1) Get an AWS account and setup the beanstalk client: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html

2) clone this repo

3) run `eb init` into the console to initialize your application/environment

4) to test locally: `eb local run -v`

5) to deploy: `eb deploy`


Helpful links:
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker_v2config.html
* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_docker-eblocal.html

### Using the Amazon EB CLI in Docker

1. Run `bin/build-eb-image`

   This will install Elastic Beanstalk's CLI in a clean Python environment and
   tag it as `amazon-eb-cli`
2. To use it:
   
   ```sh-session
   $ docker run --rm -it amazon-eb-cli -h
   usage: eb (sub-commands ...) [options ...] {arguments ...}
   
   Welcome to the Elastic Beanstalk Command Line Interface (EB CLI). 
   For more information on a specific command, type "eb {cmd} --help".
   ```
