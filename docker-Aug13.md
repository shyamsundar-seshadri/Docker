# 13 Aug - Day 2:

##To Build Image

###To build a docker image from docker file  
build nginx into Ubuntu  

Sample docker file:  
[Docker File](https://github.com/sssrox/Docker/blob/master/dockerImages/DockerFile-NginxInUbuntu)  
Nme of the docker file should be "DockerFile"  

write the docker file and execute in command line from the docker file directory as below,  
docker build -t="sssrox/nginxalpha" .  


### Change content of html in nginx and build
search through the config in nginx for site  
docker container exec -it 40683870a84c bash  
cat /etc/nginx/sites-available/default  

the value after root will be the path  
For eg here:  
root /var/www/example.com;

so navigate to that directory as working directory in docker script 
sample docker script [DockerScript](https://github.com/sssrox/Docker/blob/master/dockerImages/DockerFileAddHtmlnsideNginx)

