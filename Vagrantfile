# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "hashicorp/precise64"

  config.vm.network "private_network", ip: "192.168.0.10"
  config.vm.hostname = "local.mtheunissen82.github.io"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "mtheunissen82.github.io"
    vb.memory = "2048"
  end

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    sudo apt-get update

    # install vim
    sudo apt-get install -y vim curl

    # install latest git
    sudo apt-get install -y software-properties-common python-software-properties
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt-get update
    sudo apt-get install -y git

    # install apache httpd
    sudo apt-get install -y apache2

    # install nodejs
    sudo apt-get install -y nodejs

    # install latest rvm, latest ruby and latest rubygems
    gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
    curl -sSL https://get.rvm.io | bash -s stable
    source $HOME/.rvm/scripts/rvm
    rvm install 2.3.0
    rvm --default use 2.3.0
    gem update --system

    # install jekyll
    gem install jekyll jekyll-docs

    # install bundler
    gem install bundler
  SHELL

  # provision several usefull configuration files from guest to guest
  config.vm.provision "file", source: "~/.gitconfig", destination: ".gitconfig"
  config.vm.provision "file", source: "~/.ssh/id_rsa", destination: ".ssh/id_rsa.provisioned"
  config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: ".ssh/id_rsa.pub.provisioned"
end
