FROM centos:7
MAINTAINER Miao Luo "miaol@vmware.com"

RUN rpm --import 'https://download.ceph.com/keys/release.asc'
RUN rpm -Uvh http://download.ceph.com/rpm-kraken/el7/noarch/ceph-release-1-1.el7.noarch.rpm
RUN yum install -y epel-release && yum clean all
RUN yum install -y nfs-ganesha-vfs
RUN mkdir -p /exports
EXPOSE 2049/tcp
ADD vfs.conf /vfs.conf
ENTRYPOINT ["ganesha.nfsd", "-F", "-L", "/dev/stdout", "-f", "/vfs.conf"]
