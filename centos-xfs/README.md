# Build and run the Container with vSphere volume plugin

```bash
  # docker build -t centos/ganesha-xfs.
  # docker volume create --driver=vsphere --name=xfsVol -o size=10gb -o fstype=xfs
  # # exports volume vfsVol using the following command
  # docker run -ti --net=host --privileged  -v xfsVol:/exports centos/ganesha-xfs
  # # test mount on VM
  # mount Server_IP:/exports /mnt


"--privileged" is necessary.
