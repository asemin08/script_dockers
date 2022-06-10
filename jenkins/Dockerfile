FROM jenkins/jenkins:jdk17-preview

#need root user
USER root

# Install tools and software
RUN apt-get update && apt-get install -y software-properties-common unzip wget maven

# Install Terraform
ARG TERRAFORM_VERSION=1.2.2
RUN wget --progress=dot:mega https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip

RUN \
        unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
        mv terraform /usr/local/bin/ && \
        chmod +x /usr/local/bin/terraform && \
        terraform --version


#jenkins user
USER jenkins
