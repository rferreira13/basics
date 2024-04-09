isolamento de processo
isolamento de filesystem
gerenciamento de recurso

sudo unshare --pid --fork --mount-proc /bin/bash

ps -ef --forest

exit

mkdir container

cd container

sudo apt update && sudo apt install debootstrap 

sudo debootstrap jammy .

ls

sudo chroot .


Remote Development (VS code extension)



https://docs.docker.com/engine/install/ubuntu/

https://docs.docker.com/engine/install/linux-postinstall/


