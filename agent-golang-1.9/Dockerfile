FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11

LABEL maintainer="Okky Hendriansyah <okky.htf@gmail.com>"

# Install Golang
RUN yum update -y \
 && yum install -y centos-release-scl git go-toolset-7-golang \
 && yum clean all \
 && mkdir -p /go

ENV GOPATH=/go \
    BASH_ENV=/opt/rh/go-toolset-7/enable \
    ENV=/opt/rh/go-toolset-7/enable \
    PROMPT_COMMAND=". /opt/rh/go-toolset-7/enable"

WORKDIR /go

RUN chgrp -R 0 /go \
 && chmod -R g=u /go

