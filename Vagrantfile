Vagrant.configure("2") do |config|
  config.vm.box = "generic/centos6"
  config.vm.network "forwarded_port", guest: 5432, host: 5432
  config.vm.box_download_options = {"ssl-no-revoke" => true}
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
  config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y postgresql postgresql-server postgresql-contrib
    sudo /etc/init.d/postgresql initdb
    sudo /etc/init.d/postgresql start
  SHELL
end
