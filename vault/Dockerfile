FROM gcr.io/jenkinsxio/builder-base:0.0.81

ENV VAULT_VERSION=1.3.4
RUN wget https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip
RUN unzip vault_${VAULT_VERSION}_linux_amd64.zip && chmod +x vault && mv vault /usr/bin &&  rm vault_${VAULT_VERSION}_linux_amd64.zip
RUN vault --version

ENV JX_VERSION 2.1.30
RUN curl -f -L https://github.com/jenkins-x/jx/releases/download/v${JX_VERSION}/jx-linux-amd64.tar.gz | tar xzv && \
    mv jx /usr/bin/