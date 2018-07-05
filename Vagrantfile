Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.provision "shell", inline: <<-SHELL
    yum -y install httpd php php-mysql
    yum -y install mariadb-server

    service httpd start
    chkconfig httpd on

    service mariadb start
    chkconfig mariadb on

    ln -s -d /vagrant/html /var/www
  SHELL
end
