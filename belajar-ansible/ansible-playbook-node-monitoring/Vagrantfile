# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  ssh_pub_key = File.readlines("#{Dir.pwd}/key/vagrant-key.pub").first.strip
  config.vm.provision 'shell', inline: 'mkdir -p /root/.ssh'
  config.vm.provision 'shell', inline: "echo #{ssh_pub_key} >> /root/.ssh/authorized_keys"
  config.vm.provision 'shell', inline: "echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys", privileged: false
  
  config.vm.box = "ubuntu/focal64"
  
  #set limit specs vm virtualbox to 1 cpu & 256 mb mem
  config.vm.provider :virtualbox do |v|
    v.memory = 384
    v.cpus = 1
    v.linked_clone = true
  end

  #app-1
  config.vm.define "app-1" do |app|
    app.vm.hostname = "app-1.vagrant.local"
    app.vm.network :private_network, ip: "10.0.0.100"
  end
  #node-exporter
  config.vm.define "prometheus" do |app|
    app.vm.hostname = "prometheus.vagrant.local"
    app.vm.network :private_network, ip: "10.0.1.2"
  end

  config.vm.define "grafana" do |app|
    app.vm.hostname = "grafana.vagrant.local"
    app.vm.network :private_network, ip: "10.0.1.3"
  end
  
  config.vm.define "grafana-loki" do |app|
    app.vm.hostname = "grafana-loki.vagrant.local"
    app.vm.network :private_network, ip: "10.0.1.4"
  end

end