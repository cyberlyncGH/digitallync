# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  
  config.vm.define :aem_author do |author|
  author.vm.box = "aem_author"
  author.vm.box_url="file:///C:/Users/cyberlync/Documents/cylysetup/bento/builds/centos-7.2.virtualbox.box"
  author.vm.hostname="aem-author"
  author.vm.network "forwarded_port", guest: 4502, host: 8210
  author.vm.network "private_network", ip: "192.168.30.50"

  config.vm.provision :chef_client do |chef|
  chef.chef_server_url = "https://api.chef.io/organizations/clync"
  chef.validation_key_path = "./.chef/clync-validator.pem"
  chef.validation_client_name = "clync-validator"
  chef.node_name = "Author"
  chef.environment = "development"
  end
  end

  config.vm.define :aem_publish do |publish|
  publish.vm.box = "aem_publish"
  publish.vm.box_url = "file:///C:/Users/cyberlync/Documents/cylysetup/bento/builds/centos-7.2.virtualbox.box"
  publish.vm.hostname="aem-publish"
  publish.vm.network "forwarded_port", guest: 4503, host: 7210
  publish.vm.network "private_network", ip: "192.168.30.60"

  config.vm.provision :chef_client do |chef|
    chef.chef_server_url = "https://api.chef.io/organizations/clync"
  chef.validation_key_path = "./.chef/clync-validator.pem"
  chef.validation_client_name = "clync-validator"
  chef.node_name = "Publish"
  chef.environment = "development"
  end
  end

  config.vm.define :jenkins_master do |jenkins|
  jenkins.vm.box = "jenkins_master"
  jenkins.vm.box_url = "file:///C:/Users/cyberlync/Documents/cylysetup/bento/builds/centos-7.2.virtualbox.box"
  jenkins.vm.hostname="jenkins-master"
  jenkins.vm.network "forwarded_port", guest: 8080, host: 8282
  jenkins.vm.network "private_network", ip: "192.168.30.65"

  config.vm.provision :chef_client do |chef|
    chef.chef_server_url = "https://api.chef.io/organizations/clync"
  chef.validation_key_path = "./.chef/clync-validator.pem"
  chef.validation_client_name = "clync-validator"
  chef.node_name = "jenkinsM"
  chef.environment = "development"
 end
 end
end
