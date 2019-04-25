FROM docker.io/openshift/jenkins-slave-base-centos7:v3.11

LABEL maintainer="Okky Hendriansyah <okky.htf@gmail.com>"

RUN true \
 && set -xe \
 && yum update -y \
 && yum install -y skopeo \
 && yum clean all \
 && true

