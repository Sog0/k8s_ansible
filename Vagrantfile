VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/bookworm64"

  # Jumpbox
  config.vm.define "jumpbox" do |jumpbox|
    jumpbox.vm.hostname = "jumpbox"
    jumpbox.vm.network "private_network", ip: "192.168.56.10"
    jumpbox.vm.provider "virtualbox" do |vb|
      vb.name = "jumpbox"
      vb.memory = 512
      vb.cpus = 1
      disk_path = "E:/VMs/k8s_ansible/jumpbox_disk.vdi"
      unless File.exist?(disk_path)
        vb.customize ["createhd", "--filename", disk_path, "--size", 10240]
        vb.customize ["storageattach", :id, "--storagectl", "SATA Controller", "--port", 1, "--device", 0, "--type", "hdd", "--medium", "jumpbox_disk.vdi"]
      end
    end
  end

  # Kubernetes Master
  config.vm.define "server" do |server|
    server.vm.hostname = "server"
    server.vm.network "private_network", ip: "192.168.56.11"
    server.vm.provider "virtualbox" do |vb|
      vb.name = "server"
      vb.memory = 2048
      vb.cpus = 1
      disk_path = "E:/VMs/k8s_ansible/server_disk.vdi"
      unless File.exist?(disk_path)
        vb.customize ["createhd", "--filename", disk_path, "--size", 20480]
        vb.customize ["storageattach", :id, "--storagectl", "SATA Controller", "--port", 1, "--device", 0, "--type", "hdd", "--medium", "server_disk.vdi"]
      end
    end
  end

  # Kubernetes Node 0
  config.vm.define "node-0" do |node0|
    node0.vm.hostname = "node-0"
    node0.vm.network "private_network", ip: "192.168.56.12"
    node0.vm.provider "virtualbox" do |vb|
      vb.name = "node-0"
      vb.memory = 2048
      vb.cpus = 1
      disk_path = "E:/VMs/k8s_ansible/node0_disk.vdi"
      unless File.exist?(disk_path)
        vb.customize ["createhd", "--filename", disk_path, "--size", 20480]
        vb.customize ["storageattach", :id, "--storagectl", "SATA Controller", "--port", 1, "--device", 0, "--type", "hdd", "--medium", "node0_disk.vdi"]
      end
    end
  end

  # Kubernetes Node 1
  config.vm.define "node-1" do |node1|
    node1.vm.hostname = "node-1"
    node1.vm.network "private_network", ip: "192.168.56.13"
    node1.vm.provider "virtualbox" do |vb|
      vb.name = "node-1"
      vb.memory = 2048
      vb.cpus = 1
      disk_path = "E:/VMs/k8s_ansible/node1_disk.vdi"
      unless File.exist?(disk_path)
        vb.customize ["createhd", "--filename", disk_path, "--size", 20480]
        vb.customize ["storageattach", :id, "--storagectl", "SATA Controller", "--port", 1, "--device", 0, "--type", "hdd", "--medium", "node1_disk.vdi"]
      end
    end
  end
end
