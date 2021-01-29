FROM tomcat:8.0

ADD **/*.war /usr/local/tomcat/webapps
#RUN cp -a **/*.war /usr/local/tomcat/webapps/
EXPOSE 8080
CMD ['cataline.sh','run']
