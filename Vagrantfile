Vagrant.configure("2") do |config|
  # Ubuntu 12.02 - Precise Pangolin
  config.vm.define "ubuntu12" do |ubuntu12|
    ubuntu12.vm.box = "bento/ubuntu-12.04"
    ubuntu12.vm.hostname = "gozma12"
    ubuntu12.vm.network "private_network", ip: "192.168.27.12"
    # provisioners
    ubuntu12.vm.provision 'shell', path: './vagrant/provision/provision-common.sh'
    ubuntu12.vm.provision 'shell', path: './vagrant/provision/provision-webserver.sh'
    ubuntu12.vm.provision 'shell', path: './vagrant/provision/provision-databases.sh'
    ubuntu12.vm.provision 'shell', path: './vagrant/provision/provision-extras.sh'
    ubuntu12.vm.provision 'shell', path: './vagrant/provision/provision-cleanup.sh'
    # synced folders
    config.vm.synced_folder '.', '/vagrant', disabled: true
    config.vm.synced_folder '~/PhpStorm__Projects', '/projects', owner: 'vagrant', group: 'vagrant'
  end
end
