  VAGRANTFILE_API_VERSION = "2"

$script = <<ENDSCRIPT
    sudo yum install -y epel-release
    sudo yum -y update
    sudo yum install -y net-tools
    sudo yum install -y wget
    sudo yum install -y fontconfig java-11-openjdk
    sudo yum install -y maven
    sudo yum install -y https://packages.endpointdev.com/rhel/7/os/x86_64/endpoint-repo.x86_64.rpm
    sudo yum install -y git
ENDSCRIPT
    
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "centos/7"
    config.vm.network "forwarded_port", guest: 8080, host: 2406
    config.vm.provision "shell", inline: $script
end
