# building a stage  to build a mavan project and using ARG to name the branch name.
FROM maven:3.8.6-eclipse-temurin-11-alpine as build 
ARG BRANCH=main
ADD https://github.com/spring-projects/spring-petclinic.git  /spring-petclinic
RUN cd spring-petclinic && \
    git checkout ${BRANCH} && \
    mvn package
# creating an another openjdk 11 to run the java application 
FROM openjdk11:jdk-11.0.11_9-alpine-slim
LABEL author="testing"
LABEL openjdk="java project"
EXPOSE 8080
COPY --from=build /spring-petclinic/target/spring-petclinic-2.7.3.jar /spring-petclinic-2.7.3.jar
CMD [ "java","-jar","spring-petclinic-2.7.3.jar" ]

# getting git not found error while running the file in the build stage. fix it ...