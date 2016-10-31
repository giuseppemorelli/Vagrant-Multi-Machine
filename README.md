[![stable version](https://img.shields.io/badge/stable%20version-1.0.2-green.svg?style=flat-square)](https://github.com/gmdotnet/Vagrant-Multi-Machine/releases/tag/1.0.1)
[![develop](https://img.shields.io/badge/beta%20version-branch%20develop-oran.svg?style=flat-square)](https://github.com/gmdotnet/Vagrant-Multi-Machine/tree/develop)
[![license](https://img.shields.io/badge/license-OSL--3-blue.svg?style=flat-square)](https://github.com/gmdotnet/Vagrant-Multi-Machine/blob/master/LICENSE.txt)

# Vagrant Multi Machine

This is a simple Vagrantfile with yaml config for Multi Machine environment.

## Features

- vagrant multi machine: use for create any machine you want
- choose your favourite box
- update your file hosts automatically
- YAML config file. No more Vagrantfile to edit!
- with vagrant plugin HostsUpdater: no more /etc/hosts file to edit!

## Requirements

- virtualbox 5.x
- vagrant >1.8.4
- vagrant HostsUpdater plugin: https://github.com/cogitatio/vagrant-hostsupdater 
  install with `vagrant plugin install vagrant-hostsupdater`
- (in case of error of shared folder mount errors) vagrant vagrant-vbguest plugin (install with the command `vagrant plugin install vagrant-vbguest`)

## How to use

- download https://github.com/gmdotnet/Vagrant-Multi-Machine/archive/master.zip
- unzip on your favorite work folder
- rename `config/config.yaml.sample` in `config/config.yaml`
- change settings in `config/config.yaml`
(if you need more information about sync folder and rsync folder just have a look here: https://www.vagrantup.com/docs/synced-folders/basic_usage.html)
- run `vagrant up` on folder where is `Vagrantfile`
- (optional) make your configuration on vagrant machine entering by run `vagrant ssh`
- have fun and happy coding!

### Vagrant Box

If you want, you can use `giuseppemorelli/lamp-stack` as box to have a LAMP stack.<br />
More info in other repository: https://github.com/gmdotnet/Vagrant-LAMP

### Credits

Giuseppe Morelli - [giuseppemorelli.net](http://www.giuseppemorelli.net)