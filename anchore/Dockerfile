FROM gcr.io/jenkinsxio/builder-base:0.0.81
RUN sudo yum install -y epel-release
RUN sudo yum install -y python-pip
RUN pip install --user --upgrade anchorecli

ENV JX_VERSION 2.1.30
RUN curl -f -L https://github.com/jenkins-x/jx/releases/download/v${JX_VERSION}/jx-linux-amd64.tar.gz | tar xzv && \
    mv jx /usr/bin/