# Install centos via WSL 
 ## Basic tips
- windows Version 1903 or higher
- Enable the "Windows Subsystem for Linux" optional feature,Enable Virtual Machine feature
- Set WSL 2 as your default version

## Note
### 1. Chocolatey
> a software management solution that allows you to manage 100% of your software, anywhere you have Windows, with any endpoint management tool. 
```sh
# run powershell(administrator), close protection software
Get-ExecutionPolicy
Set-ExecutionPolicy AllSigned
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
### 2. LxRunOffline
> A full-featured utility for managing Windows Subsystem for Linux (WSL)
```sh
choco install lxrunoffline
```
reopen powershell(administrator)
### 3. Centos-WSL
```sh
wget https://github.com/CentOS/sig-cloud-instance-images/raw/CentOS-7/docker/centos-7-docker.tar.xz
LxRunOffline install -n centos -d E:/centos -f D:\centos-8-x86_64.tar.xz
LxRunOffline.exe list
```
uninstall
```sh
LxRunOffline.exe uninstall -n centos
```
### 4. WSL2
```sh
wsl -l -v
wsl --set-version centos 2
# start
wsl -d centos
uname -a
cat /proc/version
cat /etc/redhat-release
# stop
wsl --shutdown -n
```
### 5. Windows Terminal
open setting, automatically attach when saving
## Question
The above centos is not pure, how to use iso to package it yourself
## Refrence
- mb5fd86d8699f84.WSL2子系统安装CentOS8及源码编译安装Nginx1.18+PHP7.4+MySql8.0开发[EB/OL].https://blog.51cto.com/15057852/2567230, 2020.
- xmdoor.在Windows 10上使用WSL安装Centos[EB/OL].https://zhuanlan.zhihu.com/p/272735470, 2020.
- mishamosher.CentOS WSL[EB/OL]https://github.com/mishamosher/CentOS-WSL, 2020.