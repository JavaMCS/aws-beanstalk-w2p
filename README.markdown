## Install eb:

Download and unzip the Elastic Beanstalk command line tools package at the AWS Sample Code & Libraries website.

Create environment variable to run eb:

$ export PATH=$PATH:<path to unzipped eb CLI package>/eb/linux/python2.7/

## Import the project:

git clone git@github.com:javamcs/aws-beanstalk-w2p.git

## To configure Elastic Beanstalk

cd aws-beanstalk-w2p

eb init

"Available solution stacks are:" 32

Change .elasticbeanstalk/optionsettings.aws-beanstalk-w2p-env file: 

[aws:autoscaling:launchconfiguration]

EC2KeyName=<key .pem name>
InstanceType=t1.micro

and 

[aws:elasticbeanstalk:container:python]

NumProcesses=1
NumThreads=15
StaticFiles=/static/=static/,/static=applications/welcome/static/
WSGIPath=handlers/wsgihandler.py

eb start

## RDS CLI

http://docs.aws.amazon.com/AmazonRDS/latest/CommandLineReference/Welcome.html

Command RDS Free Tier
rds-create-db-instance <registration name> --multi-az false --backup-retention-period 0  --allocated-storage 20 --storage-type standard --db-instance-class db.t1.micro --engine mysql --db-name <database name> --master-username <database username> --master-user-password <database password>
