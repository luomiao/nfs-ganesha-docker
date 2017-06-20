# Build and run the Container

```bash
  # docker build -t centos/ganesha-vfs.
  # # exports /home/exports using the following command
  # docker run -ti --net=host --privileged  -v /home/exports/:/exports centos/ganesha-vfs
  # # test mount on VM
  # mount Server_IP:/exports /mnt


"--privileged" is necessary.
