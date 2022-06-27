-----------------------------
🎏~nano 

*open-file/save/exit/minimize
nano name-files.txt
save: ctrl-o
exit: ctrl-x
minimz: ctrl-z

*select/copy-paste/delete/undo-redo/search

select: alt-m-a
copy: alt-6
paste: ctrl-u
cut/delete: ctrl-k
undo: alt-u
redo: alt-e
search: ctrl-w

-----------------------------
🎏 ~tmux 

ENV

tmux source-file ~/.tmux.conf
scroll-mode/select/copy-paste/exit :q

NAV

scroll-mode: C-a+page-up (exit: q)
copy-mode: C-a+[
mark-mode: C-a+space
copy: C-w
paste: C-a+]

MISC

move-between panes: C-a+<arrow keys>
move-to next window: C-a+n
move-to prev window: C-a+p
moving-awindow: C-a+C-shift+<arrow-keys> 
view-sess&window: C-a+w or C-a+s
rename window: C-a+,
new windows: C-a+c
close window: C-a+&

tmux-command: C-a+:
:rename-session -t <current-name> <new-name>
attach temux-sess: tmux attach -t <session-name>
list-all sess: tmux list-session
detach: C-a+d

make-new sess: tmux new -s <session-name> 
split-panes(VERTICL): C-a+%
split-panes(HORIZON): C-a+"

-----------------------------
🎏~ATOM

atom-toggle-gittab: ctrl-shift-9
atom-minim-treeview:ctrl-k and ctrl-b
atom-toggle-treeview: ctrl-\

atom-close-tab: ctrl-w
atom-close-allpane: ctrl-k and ctrl-w

atom-split-panes (on-focus-tree): ctrl-k and left/right
atom-move focus (panes): ctrl-k and ctrl-left/right

-----------------------------
📦~Python virtualenv

python3 -m venv env
virtualenv env
pip freeze > requirements.txt

-----------------------------
📦~Docker

*ENV for pg
> docker run -d \
> -p port-to-bind:port \
> --name name-image \
> -e POSTGRES_USER=user-name \
> -e POSTGRES_PASSWORD=password \
> -e POSTGRES_DB=name-db \
> -v $pwd/name-dir/init.sql:/docker-entrypoint-initdb.d/init.sqp \
> postgres

*ENV docker network for pg 

docker run -d \
-p 5432:5432 \
--name todo-postgres \
-e POSTGRES_USER=postgres \
-e POSTGRES_PASSWORD=rahasia \
-e POSTGRES_DB=belajar \
-v $pwd/postgres/init.sql:/docker-entrypoint-initdb.d/init.sqp \
--network todo \
postgres

*start docker container by images
docker run name-image

*start docker container (detach/backgroud)
docker run -d name-image

*start docker container with binding port and (detach)
docker run -d -p port-id-tobind:port-id name-image

*start docker container with name,portbinding,detach
docker run -d -p port-id-tobind:port-id \
--name init-container-name \
name-image:w-optional-version

*stop/restart running a docker container
docker stop container-id
docker start container-id

*show realtime logs on running container
docker logs -f container-id 

*print logs docker container
docker logs container-id
docker logs container-name

*look some docker container on running..
docker ps

*look all logs/history run docker container
docker ps -a

*look for images
docker images

*login to a docker container
docker exec -it container-name bash

*download some images visit (https://hub.docker.com)
docker pull name-image

*delete docker image
docker rmi name-image

*delete docker container
docker rm container-id

*show docker-container mem usange
docker ps -q | xargs  docker stats --no-stream

-----------------------------
📦~Php env

sudo add-apt-repository ppa:ondrej/php
sudo apt install php7.4
sudo apt install curl php-cli php-mbstring git unzip
sudo apt install php7.4-zip php7.4-mbstring php7.4-curl php7.4-gd php7.4-xml -y
sudo apt install php7.4-xml -y
sudo update-alternatives --config php
dpkg -l | grep php | tee packages.txt

-----------------------------
📦~Go-lang

wget https://go.dev/dl/go1.15.linux-amd64.tar.gz
wget https://go.dev/dl/go1.17.6.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.15.linux-amd64.tar.gz
echo -e "# adding Go-lang env\nexport PATH=$PATH:/usr/local/go/bin"
go version
*adding go mod on project dir
go mod init <repo-name> #etc github.com/username/reponame/tree/main/namedir
*add require to go.mod
require github.com/lib/pq v1.9.0 
*pull those module localy
go mod tidy

-----------------------------
📦~repo-key list

ls /etc/apt/sources.list.d
sudo rm -i /etc/apt/souces.list.d/ppa_name.list

-----------------------------
📦~Install-packages

.deb: sudo dpkg -i name_package || sudo apt install name_package
.tar.gz: tar -xzvf rebol.tar.gz
.tar:
.rar:
.zip: unzip filename 
.zip: unzip filename.zip -d /new-dir
.iso:

-----------------------------
📦~Remove-packages

list package: sudo apt list --installed | grep grid
remove package: sudo apt remove program_name
list package (.deb): dpkg -l | grep package
remove package(.deb): dpkg -r name_package
sudo apt-get purge name-app*
sudo apt-get purge --auto-remove name-app*

-----------------------------
🎏 ~react-native 

reload-metro:r
start-metro: npx react-native start
start-emu: npx react-native run-android
emu_conf: ctrl+m

-----------------------------
🍕 make new dir  

mkdir dir

-----------------------------
🍕 rename dir

mv notebook_jep/ notebook-jep

-----------------------------
🍕 duplicate or backup dir 
🍕 (But make a new dir first!!!)

cp -a dir1/. ~/dir/dir2

-----------------------------
🍕 duplicate or backup dir (with rsync) use '--exclude' to ignore some folder/files

> rsync -avP sourcefolder/. /<destinations-folder>
> rsync -avP sourcefolder/. /<destinations-folder> --exclude /<some-dir> --exclude <some-files>

-----------------------------
🍕 move all * to other dir

mv -v dir1/* ~/dir/dir2

-----------------------------
🍕 remove dir or intance

rm -v dir1
rm -rf dir1
rm other.txt
rm -rf .git

----------------------------
🎏 ~create dummy.dat on dir

touch dummy{1..5}

---------------------------
🎏 ~Common

Change interface
TTY
> ctrl+alt+F3
GUI
> ctrl+alt+F7

group
> less /etc/group
> usermod -aG <name-group> $USER
> newgrp <name-group>

backup-mate-keybind
> dconf dump /org/mate/desktop/keybindings/ > dconf-mate-desktop-keybindings.conf
> dconf dump /org/mate/marco/window-keybindings/ > dconf-mate-marco-keybindings.conf

restore-mate-keybind
> cat dconf-mate-desktop-keybindings.conf | dconf load /org/mate/desktop/keybindings/
> cat dconf-mate-marco-keybindings.conf | dconf load /org/mate/marco/window-keybindings/

make softlink: 
> ln -s TargetFilePath Reference

other common command: 
> cat /etc/*release*
> ls /etc/apt/sources.list.d
> sudo rm -i /etc/apt/souces.list.d/ppa_name.list
> htop
> lsblk
> lscpu
> lsusb
> lspci
> pwd
> ls -a
> ls -la
> ls -lia
> ls -ltr
> sudo nano /etc/pulse/daemon.conf 
> pulseaudio --kill

Disk command status:
> sudo fdisk -l 
> lsblk 
> df -h

Mount & unmount:
> udiskctl mount -b /dev/<your-annotation-fdisk-w-num>
> udiskctl unmount -b /dev/<your-annotation-fdisk-w-num>

### Formating fdisk 

#### 1. checking fdisk list
> sudo fdisk -l

#### 2. formating fdisk filesystem
##### exp: sudo wipefs --all /dev/sdb
> sudo wipefs --all /dev/usb-annotation-name

#### 3. checking fdisk again 
> sudo fdisk -l

#### 4. creating fdisk filesystem
##### exp: sudo cfdisk /dev/sdb
> sudo cfdisk /dev/usb-annotation-name

> select dos type

> create new partition

> makeit primary

> select write -> 'yes'

> select quit

#### 5. formating partition to use
##### exp: sudo mkfs.vfat -n 'plasdis' /dev/sdb1
> sudo mkfs.vfat -n 'fdisk-lable' /dev/fdisk-annotation-name-with-anumber

---
### Creating usb bootable fdisk 

#### 1. checking fdisk list
sudo fdisk -l

#### 2. creating usb bootable
#### exp: sudo dd bs=4M if=Downloads/wtflinux.iso 0f=/dev/sdb status=progress && sync
```
sudo dd bs=4M if=<path-to-iso> of=/dev/<usb-annotation-name> status=progress && sync
```

---
### Pacman-getsize:
`pacman -Qi xfce4-terminal | grep -i size`


CWEB image
> cweb for compresing some image-webp
> cwebp -q 10 src/images/pp.jpeg -o src/images/pp-10.webp

----------------------------
~MySQL

dump database:
> sudo mysqldump -u root -p --databases nama_db > backupOfNamaDB.sql

restore database;
> sudo mysql -u root -p < backupOfNamaDB.sql

----------------------------
🎏 ~Network 

> lsof -i

> lsof -i :8080

> lsof -i :8080 | grep PID

> sudo lsof -i tcp:3000 

> ps aux | grep -i option_app

> kill -9 PID

> kill $(lsof -t -i:port)

> sudo grep psk= /etc/NetworkManager/system-connections/*

> systemctl list-unit-files '*mariadb*' '*mysql*'

> sudo systemctl disable mysql

> sudo update-rc.d apache2 disable

> systemctl disable postgresql

-----------------------------
🎏 ~Git command 

show git config:
> git config -l

show all git branches:
> git branch

swith between branch:
> git checkout name_branch_on_repo

show different between local & remote repo:
> git diff origin/name_main_or_branch

show status git:
> git status 

rename branch: 
> git branch -m master main

git remove remote origin:
> git remote remove origin

change origin
> git remote set-url origin https://github.com/user/another-repo

change origin W/ ssh: 
> git remote set-url origin git@github.com:user/repo-name.git 

common-git command:
> git init

> git add .

> git commit -m "ayo!" 

> git branch -M main 

> git remote add origin http://somegitrepos.git 

> git push -u origin main

