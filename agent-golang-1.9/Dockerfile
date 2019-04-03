FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11

LABEL maintainer="Okky Hendriansyah <okky.htf@gmail.com>"

ENV VERSION=1.9.7 \
    OS=linux \
    ARCH=amd64 \
    GOPATH=/go

RUN true \
 && set -xe \
 && yum update -y \
 && yum clean all \
 && mkdir -p /go \
 && chgrp -R 0 /go \
 && chmod -R g=u /go \
 && cd /go \
 && wget -c https://dl.google.com/go/go$VERSION.$OS-$ARCH.tar.gz \
 && tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz \
 && rm go$VERSION.$OS-$ARCH.tar.gz \
 && echo "export PATH=$PATH:/usr/local/go/bin" >> /etc/profile \
 && source /etc/profile \
 && go version \
 && true

WORKDIR /go
