# NFS Set Up

Here you will see how you can set up `NFS` file system to share resources. NFS
(Network File System) is a distributed file system protocol that allows you to
mount remote directories on your machine. Following instructions are for
`ubuntu 18.04` and later versions.

## Pre - requisites

**1. Set Up `ssh` Access**
Make sure you can do `ssh` at the remote machine/ server.

**2. Set Up Firewall**
Make sure firewall allows `OpenSSH` application to connect from and to any
machine. For this you can run following commands:
```
# To list all application.
sudo ufw app list

# Allow OpenSSH for coonection behind firewall.
sudo ufw allow OpenSSH

# Then enable firewall.
sudo ufw enable
# Type `y` and press `Enter` to proceed.

# See firewall status.
sudo ufw status
# From the output, you can see that only `OpenSSH` is allowed.

```

## NFS Installation & Configuration

### Package Installation

We will install `nfs-kernel-server` package on host and `nfs-common` package on
the client machine.

**1. On the Host Machine**
Install `nfs-kernel-server` using following commands:
```
sudo apt update
sudo apt install nfs-kernel-server
```

**2. On the Client Machine**
Install `nfs-common` using following commands:
```
sudo apt update
sudo apt install nfs-common
```

### Share desired directory to client machine

To share a directory do following steps:

1. Let's create a directory named `/var/shiv_nfs_dir_host` and change its
permission for security reasons on the host machine.
```
# Create desired directory.
sudo mkdir /var/shiv_nfs_dir_host -p

# Change its persmission to `nobody:nogroup`.
sudo chown nobody:nogroup /var/shiv_nfs_dir_host
```

2. Configure NFS exports on the host machine by editing `/etc/exports` file and
enable firewall for the client machine.
```
sudo nano /etc/exports

# Inside file add following.
/var/shiv_nfs_dir_host		client_machine_ip(rw,sync,no_subtree_check)

# Save the file and run following command to take effect on host machine.
sudo systemctl restart nfs-kernel-server

# Now allow client machine to access shared directory through firewall.
sudo ufw allow from `client_machine_ip` to any port nfs

# To verify this, type below command.
sudo ufw status
```

3. On client machine, mount this shared directory to your desired directory
using following command:
```
# Mount the shared host directory.
sudo mkdir shiv_nfs_dir_client
sudo mount `host_machine_ip`:/var/shiv_nfs_dir_host shiv_nfs_dir_client

# Check it using following command on the client machine.
df -h
```

4. After use, you can unmount the shared directory form client machine using
following command.
```
sudo umount shiv_nfs_dir_client
```

For more go to man page `man nfs`.

## Reference

Go to [this](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-18-04)
link to know more.