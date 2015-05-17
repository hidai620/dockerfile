FROM centos:7
MAINTAINER "Yoshiaki Hidai" <hidai.620@gmail.com>
ENV container docker
RUN yum -y swap -- remove fakesystemd -- install systemd systemd-libs
RUN yum -y update &&  yum clean all && \
(cd /lib/systemd/system/sysinit.target.wants/ && \
for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done) && \
rm -rf /lib/systemd/system/multi-user.target.wants && \
rm -rf /etc/systemd/system/*.wants && \
rm -rf /lib/systemd/system/local-fs.target.wants/* && \
rm -rf /lib/systemd/system/sockets.target.wants/*udev* && \
rm -rf /lib/systemd/system/sockets.target.wants/*initctl* && \
rm -rf /lib/systemd/system/basic.target.wants && \
rm -rf /lib/systemd/system/anaconda.target.wants/*
VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]
