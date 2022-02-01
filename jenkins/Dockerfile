FROM jenkins/jenkins:lts
USER root

# Install Tools and software
RUN apt-get update && apt-get install -y software-properties-common unzip wget



# Install Terraform
ARG TERRAFORM_VERSION=1.1.4
RUN wget --progress=dot:mega https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip

RUN \
        unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
        mv terraform /usr/local/bin/ && \
        chmod +x /usr/local/bin/terraform && \
        terraform --version

# drop back to the regular jenkins user - good practice
USER jenkins