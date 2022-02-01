FROM jenkins/jenkins:alpine-jdk11

RUN pwd

USER root

RUN apk update && \
    apk upgrade && \
    apk add git && \
    apk add maven && \
    apk add bash && \
    apk add unzip && \
    apk add wget && \
    apk add terraform

RUN whoami

RUN wget https://releases.hashicorp.com/terraform/1.1.4/terraform_1.1.4_linux_amd64.zip
RUN ls 
RUN unzip terraform_1.1.4_linux_amd64

RUN ls 
RUN pwd

RUN mv terraform /usr/bin/

# RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add -
# RUN apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
# RUN apt-get update && sudo apt-get install terraform


# USER jenkins
