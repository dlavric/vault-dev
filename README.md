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

```shell
git clone https://github.com/kikitux/vault-dev.git
cd vault-dev
```

### What is included?

- A `Vagrantfile` that includes an Ubuntu VM

### Start vagrant
```shell
vagrant up
```

### Check vault has been installed
```shell
which vault
```

### Connect to the VM
```shell
vagrant ssh
```

### Give yourself root permission
```shell
sudo su -
```

### Access the vagrant file created when the VM has started
```shell
cd /vagrant/
```

### Start the vault server in DEV mode
```shell
vault server -dev
```

TBC

## TODO
- [ ] have Alvaro review the README.md
 

## DONE
- [x] add `Vagrantfile`
- [x] write scripts that download `vault`
- [x] instruction how to use this repo
- [x] modify the script to install `consul`

