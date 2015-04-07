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

