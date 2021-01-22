# vault-dev

## description

This repo is my take on having a `vagrant` setup that I can use to create a `vault` in `dev` mode

## how to use this repo

In order to use this repo, the commands you need to run are

## INSTRUCTIONS

### Prerequisites

1. Install the latest version of [Vagrant](https://www.vagrantup.com/docs/installation)

2. Install [VirtualBox](https://www.virtualbox.org/)

### Clone the Repository

```
git clone https://github.com/kikitux/vault-dev.git
cd vault-dev
```

### What is included?

- A `Vagrantfile` that includes an Ubuntu VM
- A `download-vault.sh` script that will download Vault

`Vagrantfile` from this repository:
```
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provision "shell", path: "scripts/download-vault.sh"
end
```

`donwload-vault.sh` from this repository:
```
#!/usr/bin/env bash

# download vault if not installed
# put it on /usr/local/bin


which vault
if [ $? -ne 0 ]
then

    # check if unzip is installed
    # install unzip

    which unzip
    if [ $? -ne 0 ]
    then
        # unzip is not on path
        apt-get update
        apt-get install --yes unzip
    fi  

    # download vault.zip into /vagrant
    cd /vagrant
    wget https://releases.hashicorp.com/vault/1.6.1/vault_1.6.1_linux_amd64.zip

    # unzip vault into /usr/local/bin
    # add permissions to be executable
    unzip vault_1.6.1_linux_amd64.zip
    mv vault /usr/local/bin
    chmod +x /usr/local/bin/vault

fi
```

### Start vagrant
```
vagrant up
```

### Check vault has been installed
```
which vault
```

TBC

## TODO
- [ ] have Alvaro review the README.md
 

## DONE
- [x] add `Vagrantfile`
- [x] write scripts that download `vault`
- [x] instruction how to use this repo
