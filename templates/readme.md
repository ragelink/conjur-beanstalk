Deployment Topologies
=====================

There are 2 major difrerences in the topologies for each temmplate:

1) The single docker instance will just deploy a sandbox/quisckstart environment with everything you need much like the quickstart component docker-compose.yml from conjur.org. What this will do is just install everything you need in a single docker instance inside beanstalk, this should be used for dev environments or testing but would not recommend for production because if you reboot the environement or reprovision for any reason you lose the database as its abstracted inside a docker container (posgres). Alternatively you coudl create a task to regularly backup this database but within beanstalk its better to use RDS.

2) the RDS based topoloy uses an N+1 horizontal scaling pattern for the app with a vertical for the DB. Basically you start with 1 app server/instance of the client and the server app and you scale that out by adding more nodes to satisfy high availability requrements and or scaling needs. Additionally you drop the datababse into a beanstalk managed RDS that will take care of backups and HA/patching etc. This is mostly for convenience. 

Deploying an HA Conjur/Beanstalk
--------------------------------

1) create an application in beanstalk 

2) define your deployment mechanism and load balancing

3) create an RDS database for your app (size it accordingly)

4) create an environment variable for ```DATABASE_URL``` and fill in the proper postgres information IE ```postgres://username:password@$rds-instance-hostname:port/database``` and usually the ports will be ```5432``` and the default beasntalk database will be ```ebdb``` user/pass/host will be your to provide as they vary per deployment and settings

5) once this is created proceed to spin up the environemnt with the multihost Dockerrun.aws.json ```eb deplooy```, dont worry about populating the database the app does this on boot (great stuff)

6) follow the quickstart initialization from https://www.conjur.org/get-started/install-conjur.html

7) enjoy
