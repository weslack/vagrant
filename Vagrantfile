# -*- mode: ruby -*-
# vi: set ft=ruby :

$setup = <<-SCRIPT
echo "Installing stuff"
apt-get update
apt-get install -y apt-utils git vim dirmngr gnupg gnupg-agent software-properties-common python3 autoconf gcc g++ make python-dev python3-pip python-pip python3-dev gdb libssl-dev libffi-dev build-essential --fix-missing
wget -q -O- https://github.com/hugsy/gef/raw/master/scripts/gef.sh | sh
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade git+https://github.com/Gallopsled/pwntools.git@dev
wget https://ghidra-sre.org/ghidra_9.1.2_PUBLIC_20200212.zip
unzip ghidra_9.1.2_PUBLIC_20200212.zip -d /usr/bin/
rm ghidra_9.1.2_PUBLIC_20200212.zip
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "kalilinux/rolling"
  config.vm.provision "shell", inline: $setup
end
