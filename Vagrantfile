Vagrant.configure("2") do |config|
  config.ssh.insert_key = false

  $vm_gui ||= false
  $vm_memory ||= 4096
  $vm_cpus ||= 2
  $os ||= "bento/ubuntu-22.04"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = $vm_memory
    vb.cpus = $vm_cpus
  end

  config.vm.define "homations" do |master|
    master.vm.box = $os
    master.vm.network "private_network", ip: "192.168.56.7"
    master.vm.hostname = "homations"
  end
end
