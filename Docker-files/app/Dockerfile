FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install -y maven
RUN git clone https://github.com/phemmyadot/devops-project.git
RUN cd devops-project && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "project"="devops-project"
LABEL "author"="Babafemi Adojutelegan"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE /devops-project/target/*.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]