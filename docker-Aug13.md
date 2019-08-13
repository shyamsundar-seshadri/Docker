# 13 Aug - Day 2:

##To Build Image

### Case 1: To build a docker image from docker file  
build nginx into Ubuntu  

Sample docker file:  
[Docker File](https://github.com/sssrox/Docker/blob/master/dockerImages/DockerFile-NginxInUbuntu)  
Nme of the docker file should be "DockerFile"  
for some installation provide -y switch for confirmation on installation
write the docker file and execute in command line from the docker file directory as below,  
docker build -t="sssrox/nginxalpha" .  


### Case 2: Change content of html in nginx and build
search through the config in nginx for site  
docker container exec -it 40683870a84c bash  
cat /etc/nginx/sites-available/default  

the value after root will be the path  
For eg here:  
root /var/www/example.com;

so navigate to that directory as working directory in docker script 
sample docker script [DockerScript](https://github.com/sssrox/Docker/blob/master/dockerImages/DockerFileAddHtmlnsideNginx)


### Case 3: Update configuration files and download files
update port conf by copying from local for nginx  
download a zip file from internet  
copy over files from local to ubutu root directory  

[Docker Script](https://github.com/sssrox/Docker/blob/master/dockerImages/Case3-DockerFileCopyConfFiles)
Script file desc:  
  1. download php and nginx in ubuntu  
  2. update the conf file of Nginx to point to port 81  
  this is done by moving conf file from local to niginx location while building image  
  in this case it is default file in /etc/niginx/sites-enabled/default  
  3. create a folder under var in ubuntu by name downloads and download zip file in it  
   https://github.com/nginxinc/docker-nginx/archive/master.zip should be donwloaded  
   For this wget is used  
  4. copy some sample files in local folder by name 'src' into root directory  

 
## Docker Compose
It is used to combine various images and bring up and down the images
the configurations are in yml file by name docker-compose.yml
### To bring docker up & down
go to directory of compose file
docker-compose up -d
docker-compose down
[Sample compose file](https://github.com/sssrox/Docker/blob/master/compose/docker-compose.yml)
