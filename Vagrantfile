# -*- mode: ruby -*-
# vi: set ft=ruby :

####################################
##                                ##
## GMdotnet Vagrant Multi Machine ##
## Version 1.0.0                  ##
##                                ##
####################################

# Import configuration
require 'yaml'
vagrantconfig = YAML.load_file('config/config.yaml')

Vagrant.configure("2") do |config|

  vagrantconfig['gmdotnet'].each do |machine|

    config.vm.define machine['host']['vagrantbox_name'] do |vmhost|
        # Machine info
        vmhost.vm.box = machine['host']['box']
        vmhost.vm.hostname = machine['host']['hostname']

        ## Private IP Network
        vmhost.vm.network "private_network", ip: machine['host']['private_ip']

        ## Shared folders
        if machine['host']['share'] != nil
          machine['host']['share'].each do |share|
            vmhost.vm.synced_folder share['folder']['host_folder'], share['folder']['vagrant_folder'], create: true, owner: "vagrant"
          end
        end

        ## Rsync folders
        if machine['host']['rsync'] != nil
          machine['host']['rsync'].each do |rsync|
              rsyncoptions = []
              rsync['folder']['options'].each do |options|
                rsyncoptions.push(options)
              end
              vmhost.vm.synced_folder rsync['folder']['host_folder'], rsync['folder']['vagrant_folder'], type: "rsync", rsync__args: rsyncoptions
          end
        end

        ## Virtualbox options
        vmhost.vm.provider "virtualbox" do |vb|
          # RAM
          vb.memory = machine['host']['ram']
        end

    end

  end

end