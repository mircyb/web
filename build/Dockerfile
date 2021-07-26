FROM centos:latest
 
MAINTAINER YBCHOI
 
RUN yum -y install httpd
 
COPY index.html /var/www/html/
COPY startup.sh /tmp/startup.sh
RUN chmod +x /tmp/startup.sh
 
EXPOSE 80
CMD /tmp/startup.sh
