Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.define "nginx" do |nginx|
      nginx.vm.network "private_network", ip: "192.168.4.2"
      nginx.vm.provider "virtualbox" do |v|
        v.name = "nginx-vm"
      end
  end

  config.vm.define "tomcat1" do |tomcat1|
      tomcat1.vm.network "private_network", ip: "192.168.4.3"
      tomcat1.vm.provider "virtualbox" do |v|
        v.name = "tomcat1-vm"
      end
  end

  config.vm.define "tomcat2" do |tomcat2|
      tomcat2.vm.network "private_network", ip: "192.168.4.4"
      tomcat2.vm.provider "virtualbox" do |v|
        v.name = "tomcat2-vm"
      end
  end

  config.vm.provision "file", source: "key/ansible_id_rsa.pub", destination: "~/.ssh/ansible_id_rsa.pub"
  config.vm.provision "shell", inline: "cat ~/.ssh/ansible_id_rsa.pub >> ~/.ssh/authorized_keys", privileged: false

end
