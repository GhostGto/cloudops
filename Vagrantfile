Vagrant.configure("2") do |config|
  config.vm.provision "shell", inline: <<-SHELL
    echo "10.0.4.10 cloudops" >> /etc/hosts
  SHELL

  config.vm.define "cloudops" do |cloudops|
    cloudops.vm.box = "ubuntu/jammy64"
    cloudops.vm.hostname = "cloudops"
    cloudops.vm.synced_folder "~/Documents/devops-journey/cloudops-portfolio/", "/home/vagrant/cloudops"
    cloudops.vm.network "private_network", ip: "10.0.4.10"
    cloudops.vm.provider "virtualbox" do |vb|
      vb.memory = 2024
      vb.cpus = 1
    end
  end
end

