FROM centos:7
MAINTAINER Miao Luo "miaol@vmware.com"

#RUN rpm --import 'https://download.ceph.com/keys/release.asc'
#RUN rpm -Uvh http://download.ceph.com/rpm-kraken/el7/noarch/ceph-release-1-1.el7.noarch.rpm
#RUN yum install -y epel-release && yum clean all
#RUN yum install -y nfs-ganesha-xfs
RUN yum install -y xfsprogs-devel git
RUN yum install gcc git cmake autoconf libtool bison flex doxygen openssl-devel gcc-c++ libuuid-devel nfs-utils make -y
RUN git clone -b V2.4-stable https://github.com/nfs-ganesha/nfs-ganesha.git --recursive
# follow these steps to build nfs-ganesha-xfs
#	&& mkdir -p /nfs-ganesha/build \
#	&& cd /nfs-ganesha/build \
#	&& cmake -DUSE_FSAL_GPFS=OFF /nfs-ganesha/src/ \
#	&& make \
#	&& make install
RUN mkdir -p /exports
EXPOSE 2049/tcp
ADD xfs.conf /xfs.conf
#ENTRYPOINT ["ganesha.nfsd", "-F", "-L", "/dev/stdout", "-f", "/xfs.conf"]
ENTRYPOINT ["bash"]
