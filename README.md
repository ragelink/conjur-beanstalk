Welcome to the beanstalk module for conjur.

in this repo we  hope to provide a quick way to drop in and deploy conjur https://www.conjur.org/get-started/install-conjur.html into a beanstalk multi docker container... more to come.



Steps to get setup:

1) Get an AWS account and setup the beanstalk client: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install.html

2) clone this repo

3) run `eb init` into the console to initialize your application/environment

4) to test locally: `eb local run -v`

5) to deploy: `eb deploy`
