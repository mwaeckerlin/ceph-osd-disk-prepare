# Prepare Ceph OSD Device

This image is needed to fix a bug in (ceph/daemon)[https://hub.docker.com/r/ceph/daemon]: `ceph-disk` ist not installed there, so you need to prepare the disks in advance.

Define your OSD device with `OSD_DEVICE`.

Usage:

```
docker run -it --rm --name prepare-osd \
           -e OSD_DEVICE=/dev/sda \
           -v /etc/ceph:/etc/ceph \
           -v /var/lib/ceph/:/var/lib/ceph/ \
           -v /dev:/dev \
           --net=host \
           --privileged=true \
           mwaeckerlin/ceph-osd-disk-prepare
```
