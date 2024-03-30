Directories:

    /       -> root
    /home   -> user work directories
    /root   -> home directory for root user
    /bin    -> linux commands
    /lib    -> essential libraries shared by kernel
    /usr    -> install programs read only
    /boot   -> Static files, initialize OS
    /etc    -> Config system files, initialization scripts
    /proc   -> Virtual directory of system information
    /sbin   -> Used by root user, os operation
    /tmp    -> Temporary files
    /var    -> Variable data, logs, admin data, login, transition files
    /opt    -> Aditional apps and software package
    /dev    -> Devices
    /mnt    -> Mounting point for temp system files

---

Basic commands:

> [uname](https://www.ibm.com/docs/en/aix/7.2?topic=u-uname-command)
Any detail about linux kernel

> [sudo](https://kb.iu.edu/d/amyi#:~:text=The%20sudo%20command%20allows%20you,which%20the%20system%20administrator%20configures.)
Execute commands as super user

> [free](https://www.redhat.com/sysadmin/dissecting-free-command)
Check memory usage

> [shutdown](https://www.ibm.com/docs/en/aix/7.2?topic=s-shutdown-command)
Halts operating System

> [man](https://www.ibm.com/docs/en/aix/7.2?topic=m-man-command)
Provides a intruction manual (user guide) for a command

> [pwd](https://www.ibm.com/docs/en/aix/7.2?topic=p-pwd-command)
Displays the path name of the working directory

> [ls](https://www.ibm.com/docs/en/aix/7.2?topic=l-ls-command)
Displays the contents of a directory

> [mkdir](https://www.ibm.com/docs/en/aix/7.2?topic=m-mkdir-command)
Creates one or more new directories

> [cp](https://www.ibm.com/docs/en/aix/7.2?topic=c-cp-command)
Copies files

> [rm](https://www.ibm.com/docs/en/aix/7.2?topic=r-rm-command)
Removes (unlinks) files or directories

> [mv](https://www.ibm.com/docs/en/aix/7.2?topic=m-mv-command)
Moves files. Also rename a file

> [touch](https://www.ibm.com/docs/en/aix/7.2?topic=t-touch-command)
Updates the access and modification times of a file
It can also create a file when it doesn't exist

> [cat](https://www.ibm.com/docs/en/aix/7.2?topic=c-cat-command)
Concatenates or displays files

> [grep](https://www.ibm.com/docs/en/aix/7.2?topic=g-grep-command)
Searches for a pattern in a file

---

Pipe commands:

> [Pipe commands](https://www.geeksforgeeks.org/piping-in-unix-or-linux/) are a way to manipulate stdin, stdout and stderr.

Examples:

List with ls command, detailed with the flag -l, and searches word file on the output: 

> ls -l | grep file

Redirects output. Instead of the console, the output will go to sida.txt file:

> ls -l > saida.txt

Appends the output. The output will be added on the bottom of the file sida.txt file:

> ls >> saida.txt

The command 2> will redirect the stderr when an error occurs:

> mkdir non_existing_dir/non_existing_dir 2> erro.txt 

---

[Mounting points](https://www.ibm.com/docs/en/aix/7.1?topic=systems-mounting)

Mounting is used for:

- External Hard Drives or USB Drives
- Network File Systems (NFS)
- New Hard Drives or Partitions
- Encrypted Drives
- Filesystem Repair or Recovery
- Virtual File Systems

List all devices and special files in the /dev directory:

> ls -a /dev 

Figure out what is the name of your partition.

Hard drives and partitions are typically represented by device files in this directory, with names like `sdX` or `hdX`, where `X` is a letter that represents the order of the device. 

Here's how you can identify your hard disk or partition:

- For traditional spinning hard drives and SATA SSDs, device names usually start with `sd`. For example, `sda` would be the first hard drive, `sdb` the second, and so on. Partitions on these devices are represented by numbers following the device name, like `sda1`, `sda2`, etc.
- For NVMe SSDs, the device names start with `nvme`. For example, `nvme0n1` would be the first NVMe drive, and its partitions would be represented as `nvme0n1p1`, `nvme0n1p2`, etc.

To avoid seeing all loops you may use the command below, and check the name of your hard drive:

> lsblk -o NAME,TYPE | grep -v loop

mount requires a super user. Use the command:

> sudo mkdir /mnt/external_hd

> sudo mount /dev/[partition_name] /mnt/external_hd

> sudo umount /mnt/external_hd

---

Package management 

Downloading file:

Debian distributions:

- dpkg

Redhat distributions:

- rpm

1- Download package
2- Apply install command:
> sudo dpkg -i [package_name]

3- Apply remove command:
> sudo dpkg -r [package_alias]


Directly from repository:

Debian distributions:

- apt

Redhat distributions:

- yum

1- Update repositories:
> sudo apt update

2- Search repositories:
> sudo apt search [package]

3- Install:
> sudo apt install [package]

4- Remove:
sudo apt remove [package]

---

Process management

Search processes:

> ps

> ps -a

> ps -a -x

> ps aux

> pstree -p

> pstree -p | grep [process_name]

> top

> htop

Kill process:

> kill [PID]

---

SSH:

> [SSH](https://www.ssh.com/academy/ssh/command#:~:text=A%20little%20history-,SSH%20Command%20in%20Linux,SSH%20from%20a%20remote%20location.) is a secure shell protocol. The ssh command provides a secure encrypted connection between two hosts over an insecure network.


There is 2 ways to use ssh:

- User/password
- Key pair


User/password:

- Go to cloud provider
- Create an instance
- Choose password authentication
- On your local, apply command:
> ssh root@[IP_address]
- Confirm password
- Terminate connection:
> exit

Key pair:

- Must create public key, and private key
- Public key is the 'locker', private key is the 'locker key'
- Public key is placed on the server, private key on the local
- Create using [type](https://www.ssh.com/academy/ssh/host-key) [rsa](https://en.wikipedia.org/wiki/RSA_%28cryptosystem%29) using 2048 bits
> ssh-keygen -t rsa -b 2048
- Give a password to the key
- list your keys:
> ls ~/.ssh/
- id_rsa will be the private key, id_rsa.pub will be the public key
- Copy the content of your public key:
> xclip -sel clip < ~/.ssh/id_rsa.pub
- Create an instance
- Add your public key to the server
- On your local, apply command:
> ssh root@[IP_address]
- Doesn't require password, will use id_rsa