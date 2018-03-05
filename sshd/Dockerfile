# "ported" by Adam Miller <maxamillion@fedoraproject.org> from
#   https://github.com/fedora-cloud/Fedora-Dockerfiles
#
# Originally written for Fedora-Dockerfiles by
#   scollier <scollier@redhat.com>

FROM centos:centos7
LABEL maintainer="jiahut@gmail.com"

RUN yum -y update; yum clean all
RUN yum -y install openssh-server passwd; yum clean all
RUN mkdir -p /var/run/sshd

RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' 
RUN echo 'centos7' | passwd root --stdin

EXPOSE 22
RUN systemctl enable sshd
ENTRYPOINT ["/sbin/init"]
