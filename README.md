# Cuckoo-Sandbox-
cuckoo installation in ubuntu using virtual machine


### Installation of Cuckoo
```bash
$ sudo apt-get install python python-pip python-dev libffi-dev libssl-dev
$ sudo apt-get install python-virtualenv python-setuptools
$ sudo apt-get install libjpeg-dev zlib1g-dev swig
$ sudo apt-get install mongodb
$ sudo apt-get install postgresql libpq-dev
$  sudo apt install virtualbox
```

```bash
$ sudo apt-get install tcpdump apparmor-utils$ sudo groupadd pcap
$ sudo usermod -a -G pcap cuckoo
$ sudo chgrp pcap /usr/sbin/tcpdump
$ sudo setcap cap_net_raw,cap_net_admin=eip /usr/sbin/tcpdump
$ sudo groupadd pcap
$ sudo usermod -a -G pcap cuckoo
$ sudo chgrp pcap /usr/sbin/tcpdump
$ sudo setcap cap_net_raw,cap_net_admin=eip /usr/sbin/tcpdump
$ sudo apt-get install tcpdump apparmor-utils
```

```bash
$ getcap /usr/sbin/tcpdump
```

```bash
$ sudo aa-disable /usr/sbin/tcpdump

sudo pip install m2crypto
sudo usermod -a -G vboxusers cuckoo
```

#!/usr/bin/env bash

# Author: Josh Stroschein
# Source: https://askubuntu.com/questions/244641/how-to-set-up-and-use-a-virtual-python-environment-in-ubuntu
# NOTES: Run this script as: sudo -u <USERNAME> cuckoo-setup-virtualenv.sh
# Additionally, your environment may not allow the script to source bashrc and you may need to do this manually after the script completes

```bash
# install virtualenv
sudo apt-get update && sudo apt-get -y install virtualenv

# install virtualenvwrapper
sudo apt-get -y install virtualenvwrapper

echo "source /usr/share/virtualenvwrapper/virtualenvwrapper.sh" >> ~/.bashrc

# install pip for python3
sudo apt-get -y install python3-pip

# turn on bash auto-complete for pip
pip3 completion --bash >> ~/.bashrc

# avoid installing with root
pip3 install --user virtualenvwrapper

echo "export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python3" >> ~/.bashrc

echo "source ~/.local/bin/virtualenvwrapper.sh" >> ~/.bashrc

export WORKON_HOME=~/.virtualenvs

echo "export WORKON_HOME=~/.virtualenvs" >> ~/.bashrc

echo "export PIP_VIRTUALENV_BASE=~/.virtualenvs" >> ~/.bashrc

source ~/.bashrc
```

```bash
mkvirtualenv -p python2.7 cuckoo-test
sudo pip install -U pip setuptools
pip install -U cuckoo
```

```bash
sudo mkdir /mnt/win7
sudo chown cuckoo:cuckoo /mnt/win7
sudo mount -o ro,loop win7ultimate.iso /mnt/win7
sudo apt-get -y install build-essential libssl-dev libffi-dev python-dev genisoimage
```

```bash
sudo apt-get -y install zlib1g-dev libjpeg-dev
sudo apt-get -y install python-pip python-virtualenv python-setuptools swig

pip install -U vmcloak


vmcloak-vboxnet0
vmcloak init --verbose --win7x64 win7x64base --cpus 2 --ramsize 2048


vmcloak clone win7x64base win7x64cuckoo

vmcloak snapshot --count 4 win7x64cuckoo 192.168.56.101
```

```bash
vmcloak list vms
cuckoo init

cd ~/.cuckoo/
cd conf/
cuckoo community
cd conf/  
nano viirtualbox.conf (mode=gui)
while read -r vm ip; do cuckoo machine --add $vm $ip; done < <(vmcloak list vms)
(remove cuckoo1 comnplete details)
```

Open terminator:
```bash
1. cuckoo rooter --sudo --group cuckoo
//1.2.  nano routing.conf (your netwrok adapter)
//1.3. nano reporting.conf (mongodb=yes)
2. cuckoo
3. cuckoo web --host 127.0.0.1 --port 8080
4. cuckoo clean
```

