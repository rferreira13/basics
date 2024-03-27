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


Mounting points


SSH:

> [SSH](https://www.ssh.com/academy/ssh/command#:~:text=A%20little%20history-,SSH%20Command%20in%20Linux,SSH%20from%20a%20remote%20location.) is a secure shell protocol. The ssh command provides a secure encrypted connection between two hosts over an insecure network.



