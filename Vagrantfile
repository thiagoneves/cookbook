VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Box
  config.vm.box = "hashicorp/precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64_vmware_fusion.box"

  # VM config
  config.vm.provider "vmware_fusion" do |v|
    v.vmx["numvcpus"] = "1"
    v.vmx["memsize"] = "1024"
    
    # Performance 
    v.vmx["MemTrimRate"] = "0"
    v.vmx["sched.mem.pshare.enable"] = "FALSE"
  end

  # IP
  config.vm.network "private_network", ip: "192.168.50.4"

  # Network redirect
  config.vm.network :forwarded_port, guest: 3000, host: 3000    # rails
  config.vm.network :forwarded_port, guest: 9292, host: 9292    # rack
  config.vm.network :forwarded_port, guest: 4567, host: 4567    # sinatra
  config.vm.network :forwarded_port, guest: 1080, host: 1080    # mailcatcher
  config.vm.network :forwarded_port, guest: 8888, host: 8888    # jasmine
  config.vm.network :forwarded_port, guest: 3306, host: 3306    # mysql
  config.vm.network :forwarded_port, guest: 1234, host: 1234    # node
  config.vm.network :forwarded_port, guest: 5432, host: 5432    # postgresql
  config.vm.network :forwarded_port, guest: 6379, host: 6379    # redis
  config.vm.network :forwarded_port, guest: 9200, host: 9200    # elasticsearch
  config.vm.network :forwarded_port, guest: 27017, host: 27017  # mongodb
  config.vm.network :forwarded_port, guest: 80, host: 8080      # apache/nginx

end
