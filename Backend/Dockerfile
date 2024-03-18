FROM centos:7
LABEL App="Studentapp"
LABEL DevopsEngg="yash"

WORKDIR /opt/
RUN yum install java-11-openjdk -y
ADD https://dlcdn.apache.org/tomcat/tomcat-8/v8.5.99/bin/apache-tomcat-8.5.99.tar.gz /opt 
RUN tar -xzvf /opt/apache-tomcat-8.5.99.tar.gz -C /opt/

WORKDIR /opt/apache-tomcat-8.5.99/
ADD https://fordock.s3.eu-north-1.amazonaws.com/mysql-connector.jar lib/mysql-connector.jar
COPY student.war webapps/student.war
COPY ./context.xml conf/context.xml

EXPOSE 8080
CMD bin/catalina.sh start

