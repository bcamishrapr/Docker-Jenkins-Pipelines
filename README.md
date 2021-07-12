# docker-based-jenkins-pipeline

This Project is used to demonstrate the working of build agent as a docker container and how we can use it.

# Prerequisite
- You have to install 2 plugins: Docker plugin and Docker Pipeline [Reference_link](https://stackoverflow.com/questions/62253474/jenkins-invalid-agent-type-docker-specified-must-be-one-of-any-label-none) 
- Docker server should be installed on the destination server and permission properly configured for running docker cmd.

# Instruction
- You can also define in pipeline that which agent is used for running docker based pipeline using label in pipeline: 
## EXAMPLE: 
```
agent {
    docker {
        image 'maven:3.8.1-adoptopenjdk-11'
        label 'slave' // This is used to tell that run docker agent in server which is configured as a label "slave"
        args  '-v /tmp:/tmp' // This is used to define extra docker arguments
    }
    

