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
move-window -a -t 3
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

kill-session:
tmux kill-session -t <session-number>

-----------------------------
🎏~ATOM

atom-toggle-gittab: ctrl-shift-9
atom-minim-treeview:ctrl-k and ctrl-b
atom-toggle-treeview: ctrl-\

atom-close-tab: ctrl-w
atom-close-allpane: ctrl-k and ctrl-w

atom-split-panes (on-focus-tree): ctrl-k and left/right
atom-move focus (panes): ctrl-k and ctrl-left/right

------------------------------
📦~NVIM
:E -- use Explorer mode 
in Explorer mode:
D -- for delete 
d -- create new dir 
% -- create new file

Install NVIM
[nvim V0.9.5](https://github.com/neovim/neovim/releases/tag/v0.9.5)

```sh
wget https://github.com/neovim/neovim/releases/tag/v0.9.5
tar xzvf nvim-linux64.tar.gz
sudo mkdir -p /opt/nvim-linux64
cp -r ./nvim-linux64/* /opt/nvim-linux64/
sudo ln -s /opt/nvim-linux64/bin/nvim /usr/local/bin/nvim
```

Install Ubuntu Build Esential for Clang build and etc:

```sh
sudo apt update
sudo apt install build-essential
sudo apt install clang libclang-dev
sudo apt install ripgrep
sudo apt install wslu -- if using wsl
sudo apt install xsel or sudo apt install xclip -- for clipboard
```
*in wsl*
for wsl clipboard please to menu settings and add new paste key-shortcut eg: ctrl+shift+v

Install Lazygit:
[Instalation LazyGIT](https://github.com/jesseduffield/lazygit?tab=readme-ov-file#installation)

Instalation Lazygit (Ubuntu):

```sh
LAZYGIT_VERSION=$(curl -s "https://api.github.com/repos/jesseduffield/lazygit/releases/latest" | grep -Po '"tag_name": "v\K[^"]*')
curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
tar xf lazygit.tar.gz lazygit
sudo install lazygit /usr/local/bin
```

Installing Node with NVM:

```sh
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
nvm --version
nvm install 22.6.0
nvm alias default 22.6.0
nvm list
```
Installing Rust:

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Install Go Lang:
[GoLang](https://go.dev/doc/install)

----------------------------
~Insomnia REST

[Insomnia REST v2023.5.8](https://github.com/Kong/insomnia/releases?q=2023.5.8&expanded=true)

----------------------------
📦~Python virtualenv

python3 -m venv env
virtualenv env
pip freeze > requirements.txt

Make Random Secrets:
import secrets
print(secrets.token_urlsafe(12))

-----------------------------
📦~Docker

Quickstart
1. Docker Installation
ubuntu:
sudo apt-get install docker 

arch:
sudo pacman -S docker 

arch-git:
git clone https://aur.archlinux.org/docker-git.git
sudo pacman -S base-devel
cd docker-git/
makepkg -sri

2. Starting & enable docker service
sudo systemctl start docker.service
sudo systemctl enable docker.service

3. Adding User to Docker group
sudo usermod -aG docker $USER

4. Finish

*Docker-ENV-for pg
> docker run -d \
> -p port-to-bind:port \
> --name name-image \
> -e POSTGRES_USER=user-name \
> -e POSTGRES_PASSWORD=password \
> -e POSTGRES_DB=name-db \
> -v $pwd/name-dir/init.sql:/docker-entrypoint-initdb.d/init.sqp \
> postgres

*Docker-ENV-network for pg 
docker run -d \
-p 5432:5432 \
--name todo-postgres \
-e POSTGRES_USER=postgres \
-e POSTGRES_PASSWORD=rahasia \
-e POSTGRES_DB=belajar \
-v $pwd/postgres/init.sql:/docker-entrypoint-initdb.d/init.sqp \
--network todo \
postgres

*Docker-ENV-for mysql 
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:tag
docker run --name some-mysql -p 127.0.0.1:3307:3306 -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:latest

ect:
docker run --name warungApi-db -p 127.0.0.1:3307:3306 -e MYSQL_DATABASE=db_laravel_api -e MYSQL_USER=laravel -e MYSQL_PASSWORD=my_secret -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mariadb:10.6

*Docker-Backup Mysql:
docker exec ContinerID /usr/bin/mysqldump -u root --password=my-secret-pw DATABASE-NAME> backup.sql

*Docker-Restore Mysql DB:
cat backup.sql | docker exec -i CONTAINER /usr/bin/mysql -u root --password=root DATABASE

*Docker-Test-Runing MySQL db:
docker run --name some-mysql \
-p 127.0.0.1:3307:3306 \
-e MYSQL_DATABASE=laravel_data \
-e MYSQL_USER=laravel \
-e MYSQL_PASSWORD=my-secret-pw \
-e MYSQL_ROOT_PASSWORD=my-secret-pw \
-d mariadb:10.6 

*Docker-start docker container by images
docker run name-image

*Docker-start docker container (detach/backgroud)
docker run -d name-image

*Docker-start docker container with binding port and (detach)
docker run -d -p port-id-tobind:port-id name-image

*Docker-start docker container with name,portbinding,detach
docker run -d -p port-id-tobind:port-id \
--name init-container-name \
name-image:w-optional-version

*Docker-stop/restart running a docker container
docker stop container-id
docker start container-id

*Docker-show realtime logs on running container
docker logs -f container-id 

*Docker-print Docker-logs docker container
docker logs container-id
docker logs container-name

*Docker-look some docker container on running..
docker ps

*Docker-look all logs/history run docker container
docker ps -a

*Docker-look for images
docker images

*Docker-look for images with grep:
docker images | grep 'docker_image_name'

*Docker-login to a docker container
*Docker-exec
docker exec -it container-name bash

*Docker-download some images visit (https://hub.docker.com)
docker pull name-image

*Docker-delete docker image or
*Docker-remove docker image
docker rmi name-image

*Docker-delete docker container or
docker rm container-id

*Docker-remove images with grep:
docker rmi $(docker images | grep 'docker_names')

*Docker-show docker-container mem usange
docker ps -q | xargs  docker stats --no-stream

*Docker-tag Docker-Metadata:
docker tag imagename imagename:v1.0

*Docker-compose:
docker-compose up --build -d
docker-compose down 

-----------------------------
📦~Php env

php-env-wsl2:
(setup env php7.4 or php8.2)
sudo apt install -y php7.4 php7.4-cli php7.4-common php7.4-mbstring php7.4-xml php7.4-curl php7.4-zip php7.4-mysql
sudo apt install -y php8.2 php8.2-cli php8.2-common php8.2-mbstring php8.2-xml php8.2-curl php8.2-zip php8.2-mysql
(set alternative init)
sudo update-alternatives --install /usr/bin/php php /usr/bin/php7.4 74
sudo update-alternatives --install /usr/bin/php php /usr/bin/php8.2 82
(chose default use)
sudo update-alternatives --config php

php-etc:
sudo add-apt-repository ppa:ondrej/php
sudo apt install php7.4
sudo apt install curl php-cli php-mbstring git unzip
sudo apt install php7.4-zip php7.4-mbstring php7.4-curl php7.4-gd php7.4-xml -y
sudo apt install php7.4-xml -y
sudo update-alternatives --config php
dpkg -l | grep php | tee packages.txt

https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-laravel-with-lemp-on-ubuntu-18-04
https://www.digitalocean.com/community/tutorials/how-to-install-php-8-1-and-set-up-a-local-development-environment-on-ubuntu-22-04

Manage Multiple PHP version
https://gist.github.com/michaelbutler/4a89bb23e2d30f1b0585b98d2b67cf55?permalink_comment_id=4133009

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
.zip: zip -r data.zip data/ 
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
📦~Laravel
*env log storage permission:
sudo chmod -R 775 storage && sudo chmod -R ugo+rw storage

*basic permission
sudo chown -R www-data.www-data /var/www/travellist/storage
sudo chown -R www-data.www-data /var/www/travellist/bootstrap/cache

sudo chown -R $USER:www-data storage
sudo chown -R $USER:www-data bootstrap/cache

sudo chown -R www-data:www-data /path/to/your/project/vendor
sudo chown -R www-data:www-data /path/to/your/project/storage

chmod -R 775 storage
chmod -R 775 bootstrap/cache

sudo usermod -a -G www-data userName

*create new project:
composer create-project --prefer-dist laravel/laravel
composer create-project laravel/laravel:^8.0 example-project
composer create-project laravel/laravel:^9.0 example-project

https://lindevs.com/code-snippets/generate-pem-encoded-pkcs8-format-rsa-key-pair-using-php

seeder: -- adding Model on ./database/seeder/DatabaseSeeder.php 
then create command:

User::create([
   'name' => 'admin',
   'email' => 'admin@example.com',
   'password' => bcrypt('cyberadmin') 
]);

and run
php artisan db:seed

make new route-resource:
php artisan make:controller NamaController --resource

make new model & migration db:
php artisan make:model -m NamaModel

*make model & migration db advance: (-m migration, -c controller, -r resource-controller)
php artisan make:model NamaModel -mc

*add field or new column migration:
php artisan make:migration AddNewColumToReferenceTable --table=tableName
example:
php artisan make:migration AddRoleToUsersTable --table=users

migrate db: drop all table on db and run migrate (BE CAREFULL!!)
php artisan migrate:fresh

migrate db: rollback all listed migration and run migrate
php artisan migrate:refresh

migrate db spesifik:
php artisan migrate --path=/database/migrations/fileName.php

migrate refresh rollback and then run seeder:
php artisan migrate:refresh --seed

migrate seed spesifik:
php artisan db:seed --class=/database/seeders/classNameTableSeeder.php

clear-cache:
php artisan route:clear
php artisan config:clear

dateformat:
https://www.digitalocean.com/community/tutorials/easier-datetime-in-laravel-and-php-with-carbon
https://www.php.net/manual/en/datetime.format.php
---
GO TELEPORT

Manage teleport users
https://github.com/gravitational/teleport/discussions/11820

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

over-ssh
dowmload to lokal
rsync -chavzP --stats user@remote.host:/path/to/copy /path/to/local/storage

over-ssh lokal push ke remote
rsync -av -e 'ssh -p 222' /home/user/lokal_dir user-remote@host-name:/home/host/destination

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

📦~Driver Graphics

nvidia:
1. on grub menu press key 'e'
2. find this:
linux   /boot/vmlinuz-linux root= ... log level=3 nowatchdog ...
3. add "nouveau.blacklist=yes modprobe.blacklist=nouveau" before log level
4. it's should look like this:
linux   /boot/vmlinuz-linux root= ... nouveau.blacklist=yes modprobe.blacklist=nouveau log level=3 ...
5. save with Ctrl+x 

Change backgroud login screen:
/etc/lightdm/slick-greeter.conf -> background=/path/to/picture
first cp picture to /usr/share/backgrouds

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
> ln -s SourcefilePath newsoftlinkPath

softlink win 64_32:
> mklink /D C:\TempatDokumen D:\FolderAsli

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
> ls -tl | head -5
> sudo nano /etc/pulse/daemon.conf 
> pulseaudio --kill

*Find-files with pattern:
find . -iname '*name-file*'

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
### reset arch key (using usb-bootable):

mkdir /mnt/arch
mount /dev/sda1 /mnt/arch
cd mnt/arch 
ls 
mount -t proc proc proc/
mount -t sysfs sys sys/
mount -o bind /dev dev/
mount -t devpts pts dev/pts/
chroot /mnt/arch /usr/bin/bash
passwd <user_name> 

----------------------------
~MySQL

dump database:
> sudo mysqldump -u root -p --databases nama_db > backupOfNamaDB.sql

restore database;
> sudo mysql -u root -p < backupOfNamaDB.sql

Installing mysql:
sudo apt install mysql-server
sudo mysql_secure_installation

Installing mariadb:
sudo apt install mariadb-server
sudo mysql_secure_installation

GRANT ALL ON database_name.* TO 'username'@'localhost_or_%_for_all_connection' IDENTIFIED BY 'password' WITH GRANT OPTION;

show all user access: (root)
SELECT user,host FROM mysql.user;

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
#### NGINX Conf

Access log:
https://eddmann.com/posts/processing-apache-and-nginx-access-logs/

-----------------------------
#### SSH Key generate

1. 
ssh-keygen -t ed25519 -C "nama_credential_atau_email"

2.
masukkan password

3.
eval "$(ssh-agent)"

4.
ssh-add ~/.ssh/nama_key

5.
ssh-copy -i ~/.ssh/nama_key.pub <nama_user@ipaddr>
ssh-copy -i ~/.ssh/nama_key.pub <nama-domain>
ssh-copy -i ~/.ssh/nama_key.pub -p <nomer-port> <nama_user@ipaddr> 

6. 
buat config di ~/.ssh

7. isi konten ~/.ssh/config:
Host nama_host_sebagai_tag 
  Hostname <ip atau domain> 
  IdentityFile ~/.ssh/nama_key
  User <root atau username yg ada di server>
  Port <nomer port opsional>

8. 
ssh nama_host_sebagai_tag

9.
finish

#### SSH Key generate (Windows)

1. show ssh-agent status:
Get-Service -Name ssh-agent

2. set ssh-agent startup:
Get-Service -Name ssh-agent | Set-Service -StartupType Manual

3. start ssh-agent:
Start-Service ssh-agent

4. add identity:
ssh-add /your/ssh/conf/path

5. enter passprase

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

#Remove from repo only
#Remove a single file
git rm --cached password.txt

# Remove a single folder
git rm --cached -rf .idea

# Remove both from local & repo
# Remove a single file
git rm password.txt

# Remove a single folder
git rm -rf .idea

### wsl 
mount local data:
cd /mnt/c/Users/<windows.username>/Pictures
access wsl dir:
\\wsl$
https://www.howtogeek.com/426749/how-to-access-your-linux-wsl-files-in-windows-10/

### Wondows
cd to directory:
cd /d <to/path/of/dir>
exp: cd /d D:/data/Pictures

📦~Server

change hostname:
hostnamectl set-hostname new-hostname

add user:
useradd -m <USERNAME>
adduser --create-home <USERNAME>
adduser --home /home/<USERNAME> <USERNAME>

remove user:
deluser newuser
deluser --remove-home newuser

edit/add password:
passwd <USERNAME>

add sudoer:
usermod -aG sudo <USERNAME>

disable su for USER:
https://www.tecmint.com/disable-su-access-sudo-users/
Cmnd_Alias DISABLE_SU = /bin/su
%admin ALL=(ALL) ALL, !DISABLE_SU
<USERNAME> ALL=(ALL) NOPASSWD: ALL, !DISABLE_SU

show users config:
visudo


📦~Server static ip config on wlan

AlwaysOnDisplay:
/etc/systemd/logind.conf 
#HandleLidSwitch=suspend -> HandleLidSwitch=ignore
LidSwitchIgnoreInhibited=no 
sudo service systemd-logind restart

wifi-connect direct:
https://itsfoss.com/connect-wifi-terminal-ubuntu/

setting wifi static-ip on (/etc/netplan/50-cloud-init.yaml):
1. reserve ip & mac on router settings..
2. touch /etc/netplan/50-cloud-init.yaml
3. copy:

network:
  version: 2
  renderer: networkd
  ethernets:
    <ETH-DRIVER>:
      dhcp4: true
      optional: true
  wifis:
    <WIFI-DRIVER>:
      dhcp4: no
      optional: true
      addresses: [<IP-ADDRES>/<MASK>]
      routes:
        - to: default
          via: <GATEWAY>
      nameservers:
        addresses: [1.1.1.1, 1.0.0.1]
      access-points:
        "<SSID>":
          password: "<SSID-PASSWORD>"

~Server check DNS Resolver
In Ubuntu 18.04 and 20.04 you can use systemd-resolve --status. In newer versions use resolvectl status

~Server security sshd hardening
[basic sshd service security](https://www.wikihow.life/Secure-an-Ubuntu-Server)

📦~Server adding new partition hardisk

[Adding new partition HDD to server](https://linuxconfig.org/how-to-add-new-disk-to-existing-linux-system)
[check hdd](https://www.digitalocean.com/community/tutorials/how-to-partition-and-format-storage-devices-in-linux)
