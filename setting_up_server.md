1. Install sudo and adding new user to sudo group
```console
github@shaggy-axel$ #login as root user
github@shaggy-axel$ apt update && apt install sudo
github@shaggy-axel$ adduser <username>
github@shaggy-axel$ adduser <username> sudo
```
2. Logout and login as new user
```console
github@shaggy-axel$ sudo apt update && sudo apt install vim git
github@shaggy-axel$ sudo vim /etc/ssh/sshd_config
github@shaggy-axel$ #Change `PermitRootLogin yes` to `PermitRootLogin no`
```
3. Logout and create ssh keys
```console
github@shaggy-axel$ ssh-keygen
github@shaggy-axel$ #... if you blank lines, keys will be in `~/.ssh/`
github@shaggy-axel$ #and you can cat this:
github@shaggy-axel$ cat ~/.ssh/id_rsa # Private Key
github@shaggy-axel$ cat ~/.ssh/id_rsa.pub # Public Key
```
4. Login and turn off Password Authentication
```console
github@shaggy-axel$ #replace `~/.ssh/id_rsa` to your path to key
github@shaggy-axel$ #default port is 22, you can blank this option
github@shaggy-axel$ ssh -i ~/.ssh/id_rsa <username>@<host> -p <port>
github@shaggy-axel$ sudo vim /etc/ssh/sshd_config
github@shaggy-axel$ #Replace `PasswordAuthentication yes` to `PasswordAuthentication no`
```
5. Install Docker, Docker-compose, Python
* [Docker](https://docs.docker.com/engine/install/ubuntu/)
* [docker-compose](https://www.digitalocean.com/community/tutorials/how-to-install-docker-compose-on-ubuntu-18-04-ru)
* [python3.10](https://computingforgeeks.com/how-to-install-python-on-ubuntu-linux-system/)
