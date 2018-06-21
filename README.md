# instructions 

1. get flask app running in docker container and demonstrate that you can test it locally 
	* try to make the docker image as small as possible and make it build as quickly as possible 

2. once the flask app is running we will manually push it to dockerhub 

3. next launch an ec2 instance in aws without using the console at all. The idea here is to get the arguments you need (ie vpc subnets, ssh key etc) via cli output 

4. ssh to the instance , run the image locally, access the site via public internet

5. set up travis ci to do all of that including unit tests 

6. theres a bug in the flask app go fix it
