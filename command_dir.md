-----------------------------
📦Python virtualenv
python3 -m venv env
virtualenv env
-----------------------------
📦Install-packages
.deb: sudo dpkg -i name_package || sudo apt install name_package
.tar.gz: tar -xzf rebol.tar.gz
.tar:
.rar:
.zip: unzip filename
.iso:
-----------------------------
📦Remove-packages
list package: sudo apt list --installed | grep grid
remove package: sudo apt remove program_name
list package (.deb): dpkg -l | grep package
remove package(.deb): dpkg -r name_package
-----------------------------
🎏 nano open-file/save/exit/minimize
nano name-files.txt
save: ctrl-o
exit: ctrl-x
minimz: ctrl-z
-----------------------------
🎏 nano select/copy-paste/delete/undo-redo/search
select: alt-m-a
copy: alt-6
paste: ctrl-u
delete: ctrl-k
undo: alt-u
redo: alt-e
search: ctrl-w
-----------------------------
🎏 tmux scroll-mode/select/copy-paste
scroll-mode: ctrl+b, page-up
copy-mode: ctrl+b, [
mark-mode: ctrl+space
copy: ctrl+w
paste: ctrl+b, ]
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
🍕 move all * to other dir
mv -v dir1/* ~/dir/dir2
-----------------------------
🍕 remove dir or intance
rm -v dir1
rm -rf dir1
rm other.txt
rm -rf .git
----------------------------
🎏 create dummy.dat on dir
touch dummy{1..5}
---------------------------
🎏 Common
cat /etc/*release*
ls /etc/apt/sources.list.d
sudo rm -i /etc/apt/souces.list.d/ppa_name.list
htop
lsblk
lscpu
lsusb
lspci
pwd
ls -a
sudo nano /etc/pulse/daemon.conf 
pulseaudio --kill
🎏 Network 
lsof -i
lsof -i :8080
lsof -i :8080 | grep PID
sudo lsof -i tcp:3000 
ps aux | grep -i <option_app>
kill -9 <PID>
kill $(lsof -t -i:port)
sudo grep psk= /etc/NetworkManager/system-connections/*
systemctl list-unit-files '*mariadb*' '*mysql*'
sudo systemctl disable mysql
sudo update-rc.d apache2 disable
systemctl disable postgresql
-----------------------------
🎏 Git command
git init
git add .
git commit -m "ayo!"
git branch -M main
git remote add origin http://somegitrepos.git
git push -u origin main

