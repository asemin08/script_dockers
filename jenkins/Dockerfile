FROM jenkins/jenkins:lts

RUN pwd

USER root

RUN \
# Update
apt-get update -y && \
# Install Unzip
apt-get install unzip -y && \
# need wget
apt-get install wget -y && \
# vim
apt-get install maven -y

RUN whoami

RUN wget https://releases.hashicorp.com/terraform/1.1.4/terraform_1.1.4_linux_amd64.zip

RUN unzip terraform_1.1.4_linux_amd64

RUN ls 
RUN pwd

# RUN curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add -
# RUN apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
# RUN apt-get update && sudo apt-get install terraform


# USER jenkins
