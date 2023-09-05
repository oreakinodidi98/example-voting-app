############################# info #################################
# worker is a java file 
# so can use a maven image 
# base image maven:3.5.2-jdk-8-alpine
# work directory /code
# build instruction mvn package -D skipTests
# build is in target directory
# ports N/A
# runtime image openjdk:8-jre-alpine
# launch command java -jar target/worker-jar-with-dependencies.jar
# docker exec bash

###########################################################################
# build dockerfile 
# enter directory where dockerfile is located -> so worker
# docker image build -t oreakinodidi/workerapp-maven:v1 .
# docker run -it --rm oreakinodidi/workerapp-maven:v1
# docker ps -l to see if container is running

############## Multi stage docker file #############################
# include AS build 
# FROM oreakinodidi/workerapp-maven:v0.1.0 AS build
# include base image for run
# FROM openjdk:8-jre-alpine AS run
# Set the application directory as run directory
# WORKDIR /run
# copy artifact from build stage (/code/target/worker-jar-with-dependencies.jar) into run directory (worker.jar)
# COPY --from=build /code/target/worker-jar-with-dependencies.jar worker.jar
# run command in target directory
# CMD java -jar worker.jar
# docker image build -t oreakinodidi/workerapp-maven:v2 .
# docker run -it --rm oreakinodidi/workerapp-maven:v2
# docker ps -l to see if container is running