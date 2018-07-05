Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vbguest.auto_update = false
  config.vm.provision "shell", inline: <<-SHELL
    yum -y install httpd php php-mysql
    yum -y install mariadb-server

    systemctl start httpd.service
    systemctl enable httpd.service

    systemctl start mariadb.service
    systemctl enable mariadb.service

    rm -rf /var/www/html
    ln -s -d /vagrant/html /var/www
  SHELL
  config.vm.provision :shell, run: "always", :inline => <<-EOT
    systemctl start httpd.service
    systemctl start mariadb.service
  EOT
end
