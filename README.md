Base image for private/internal use Homelab (bootable) container applications
=============================================================================


### Virtual Machine

```shell
$ wget https://github.com/gbraad-homelab/private-base/releases/download/latest/disk.qcow2 \
     -O base.qcow2
$ sudo virt-install \
    --name base --os-variant fedora-eln \
    --cpu host --vcpus 4 --memory 4096 \
    --import --disk ./base.qcow2,format=qcow2
```


#### Update
To update the base or application, you can use the `bootc update`-command.

```shell
$ ssh admin@<ip>
$ sudo bootc update
```


#### Switch
To change the base to a specific application, you can use the `bootc switch`-command.

```shell
$ ssh admin@<ip>
$ sudo bootc switch ...
```

Possible values:

  - [ghcr.io/gbraad-homelab/forgejo-bootc](https://github.com/gbraad-homelab/personal-forgejo)
  - [ghcr.io/gbraad-homelab/jellyfin-bootc](https://github.com/gbraad-homelab/personal-jellyfin)
  - [ghcr.io/gbraad-homelab/nextcloud-bootc](https://github.com/gbraad-homelab/personal-nextcloud)
  - [ghcr.io/gbraad-homelab/homeassistant-bootc](https://github.com/gbraad-homelab/personal-homeassistant)
  - ...
