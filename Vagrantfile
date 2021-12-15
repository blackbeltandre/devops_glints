Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: "apt-get update && apt-get install -y docker.io"
  config.ssh.forward_agent = true
   config.ssh.insert_key = false 


  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/xenial64"
    master.vm.network "private_network",ip: "192.168.100.3"
      master.vm.provider "virtualbox" do |v|
        #v.gui = true
        v.memory = 2024
        v.cpus = 4
    end
  end


 config.vm.define "worker" do |worker|
    worker.vm.box = "ubuntu/xenial64"
    worker.vm.network "private_network",ip: "192.168.100.4"
    worker.vm.provider "virtualbox" do |v|
        #v.gui = true
        v.memory = 2024
        v.cpus = 2
     end  
  end
end
# vagrant up --provider virtualbox
