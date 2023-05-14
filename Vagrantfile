# -*- mode: ruby -*-
# vi: set ft=ruby :


cluster = {
  "master" => { :ip => "192.168.100.10", :cpus => 2, :mem => 4096 , :hostname => "master.home"},
  "worker1" => { :ip => "192.168.100.11", :cpus => 2, :mem => 4096 , :hostname  => "worker1.home"},
  "worker2" => { :ip => "192.168.100.12", :cpus => 2, :mem => 4096 , :hostname  => "worker2.home"},
  "worker3" => { :ip => "192.168.100.13", :cpus => 2, :mem => 4096 , :hostname  => "worker3.home"}
}
 
Vagrant.configure("2") do |config|
  cluster.each_with_index do |(hostname, info), index|
    config.vm.define hostname do |cfg|
      cfg.vm.provider :libvirt do |vb, override|
        config.vm.box = "debian/bullseye64"
        override.vm.network :private_network, ip: "192.168.100.#{index+10}"
        override.vm.hostname = hostname
        vb.memory = 4096
        vb.cpus = 2
      end # end provider
      config.vm.provision "ansible" do |ansible|
        ansible.verbose = "v"
        ansible.playbook = "playbook.yml"
      end 
    end # end config
  end # end cluster
end