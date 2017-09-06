Vagrant.configure("2") do |config|

  config.vm.define "haproxy" do |lb|
    lb.vm.box = "ubuntu/trusty64"
    lb.vm.hostname = 'haproxy'
    lb.vm.network :private_network, ip: "192.168.56.107"
    lb.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = 'web'
    web.vm.network :private_network, ip: "192.168.56.108"
    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

  config.vm.define "web1" do |web|
    web.vm.box = "ubuntu/trusty64"
    web.vm.hostname = 'web1'
    web.vm.network :private_network, ip: "192.168.56.109"
    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.hostname = 'db'

    db.vm.network :private_network, ip: "192.168.56.110"

    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

  config.vm.define "db1" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.hostname = 'db1'
    db.vm.network :private_network, ip: "192.168.56.111"
    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

  config.vm.define "db2" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.hostname = 'db2'
    db.vm.network :private_network, ip: "192.168.56.112"
    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end

end
