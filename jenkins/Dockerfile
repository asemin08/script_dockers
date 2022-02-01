FROM jenkins/jenkins:lts

RUN \
# Update
apt-get update -y && \
# Install Unzip
apt-get install unzip -y && \
# need wget
apt-get install wget -y && \
# vim
apt-get install maven -y

RUN wget https://releases.hashicorp.com/terraform/1.1.4/terraform_1.1.4_linux_amd64.zip

RUN unzip terraform_0.11.11_linux_amd64.zip

RUN mv terraform /usr/local/bin/

