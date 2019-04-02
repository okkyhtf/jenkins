FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11
LABEL maintainer="Okky Hendriansyah <okky.htf@gmail.com>"
MAINTAINER Gabe Montero <gmontero@redhat.com>

ENV MAVEN_VERSION=3.5 \
    GRADLE_VERSION=4.2.1 \
    BASH_ENV=/usr/local/bin/scl_enable \
    ENV=/usr/local/bin/scl_enable \
    PROMPT_COMMAND=". /usr/local/bin/scl_enable" \
    PATH=$PATH:/opt/gradle/bin

# Install Golang
RUN yum -y update && yum clean all

RUN mkdir -p /go && chmod -R 777 /go && \
    yum install -y centos-release-scl && \
    yum -y install git go-toolset-7-golang && yum clean all

ENV GOPATH=/go \
    BASH_ENV=/opt/rh/go-toolset-7/enable \
    ENV=/opt/rh/go-toolset-7/enable \
    PROMPT_COMMAND=". /opt/rh/go-toolset-7/enable"

WORKDIR /go

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
