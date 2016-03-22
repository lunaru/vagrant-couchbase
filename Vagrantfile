# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "node1" do |node|
    node.vm.box = "trusty64"
    node.omnibus.chef_version = "12.4.1"

    node.vm.network "forwarded_port", guest: 80, host: 8080
    node.vm.network "private_network", ip: "88.88.88.11"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "libssl"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "version" => "2.1.1",
            "memory_quota_mb" => 256
          }
        }
      }
    end
  end

  config.vm.define "node2" do |node|
    node.vm.box = "precise64"
    node.omnibus.chef_version = "12.4.1"

    node.vm.network "forwarded_port", guest: 80, host: 8081
    node.vm.network "private_network", ip: "88.88.88.12"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "libssl"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "version" => "2.1.1",
            "memory_quota_mb" => 256
          }
        }
      }
    end
  end

  config.vm.define "node3" do |node|
    node.vm.box = "precise64"
    node.omnibus.chef_version = "12.4.1"

    node.vm.network "forwarded_port", guest: 80, host: 8082
    node.vm.network "private_network", ip: "88.88.88.13"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "libssl"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "version" => "2.1.1",
            "memory_quota_mb" => 256
          }
        }
      }
    end
  end
end
