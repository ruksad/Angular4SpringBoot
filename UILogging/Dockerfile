#This statement is used to denote the base image that our new Docker
#image will be using. In the above example, we have used the OpenJDK 8 image.
# This is a very lightweight option to run Java applications
FROM openjdk:8-jdk-alpine

#This instruction is used to add some type of meta-data to the image.
#In this case we added the meta-data called MAINTAINER.
LABEL maintainer="scary coders"

# The Volume instructions creates a mount point in the container.
#You can also map a mount point to a directory on the Host OS.
#A typical use-case of volumes is to store log files generated by our application.
VOLUME /tmp

#This is an important instruction.
#It allows us to expose a particular port to the outside world. In our example, we expose Port 8080
EXPOSE 8080

# This instruction is used to define a variable with a default value.
#In our case, we are setting it to the location of the JAR file.
ARG JAR_FILE=target/UILogging-0.0.1-SNAPSHOT.jar

#In this instruction, we are basically copying files and directories to our docker image.
ADD ${JAR_FILE} spring-boot-starter.jar

#ENTRYPOINT is where you configure how the application should be executed.
#In our case, we are specifying how to run the JAR file.
ENTRYPOINT ["java","-jar","/spring-boot-starter.jar"]