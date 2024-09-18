FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y 
RUN git clone https://github.com/dilafar/sample-app-devops-practice.git
RUN cd sample-app-devops-practice && git checkout master && mvn clean install

FROM tomcat:9-jre11
LABEL Author="Fadhil"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE sample-app-devops-practice/target/vprofile-v2.war  /usr/local/tomcat/webapps/ROOT.war
WORKDIR /usr/local/tomcat/
VOLUME [ "/usr/local/tomcat/webapps" ]
EXPOSE 8080
CMD [ "catalina.sh", "run" ]
