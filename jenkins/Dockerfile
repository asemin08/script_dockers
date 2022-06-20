FROM jenkins/jenkins:jdk17-preview

#need root user
USER root

# Install tools and software
RUN apt-get update && apt-get install -y software-properties-common unzip wget maven lsb-release

RUN groupadd docker
RUN gpasswd -a jenkins docker

# Install Terraform
ARG TERRAFORM_VERSION=1.2.2
RUN wget --progress=dot:mega https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip

RUN \
        unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
        mv terraform /usr/local/bin/ && \
        chmod +x /usr/local/bin/terraform && \
        terraform --version


# Install docker 


RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg
RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list
RUN apt-get update && apt-get install -y docker-ce-cli

#RUN groupadd docker

RUN usermod -aG docker jenkins

#jenkins user
#USER jenkins
