# vagrant-libvirt-ansible
My test of doing vagrant-libvirt-ansible to deploy test enviroment.

The reason for The CPU and memmory count is I have a Rysen 9 3900x  12 core 24 thread and 64GB RAM.
but you can ajust accordingly.
````
```json 
  cluster = {
  "master" => { :ip => "192.168.100.10", :cpus => 2, :mem => 4096 , :hostname => "master.home"},
  "worker1" => { :ip => "192.168.100.11", :cpus => 2, :mem => 4096 , :hostname  => "worker1.home"},
  "worker2" => { :ip => "192.168.100.12", :cpus => 2, :mem => 4096 , :hostname  => "worker2.home"},
  "worker3" => { :ip => "192.168.100.13", :cpus => 2, :mem => 4096 , :hostname  => "worker3.home"}
}
```
````
