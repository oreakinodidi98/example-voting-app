# worker app is written in maven, so we need to use maven base image
# Using official maven runtime as base image , maven 3.5.2-jdk-8-alpine . 
# use this when manually building image 

# multi stage, with build to create artifact
FROM oreakinodidi/workerapp-maven:v0.1.0 AS build
# Set the application directory
WORKDIR /code
# copy source code into container
COPY . .
# Install our requirements
RUN mvn package -D skipTests
# launch command

# multi stage, with run to run artifact. set base image to openjdk:8-jre-alpine 
FROM openjdk:8-jre-alpine AS run
# Set the application directory as run directory
WORKDIR /run
# copy artifact from build stage (/code/target/worker-jar-with-dependencies.jar) into run directory (worker.jar)
COPY --from=build /code/target/worker-jar-with-dependencies.jar worker.jar
# run command in target directory
CMD java -jar worker.jar