# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "node1" do |node|
    node.vm.box = "trusty64"
    node.omnibus.chef_version = "12.4.1"
    config.berkshelf.enabled = true
    config.berkshelf.berksfile_path = 'bootstrap/Berksfile'

    node.vm.network "private_network", ip: "88.88.88.11"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "password" => "hocuspocus",
            "version" => "4.0.0",
            "memory_quota_mb" => 256,
            "package_full_url" => "http://packages.couchbase.com/releases/4.0.0/couchbase-server-community_4.0.0-ubuntu14.04_amd64.deb"
          }
        }
      }
    end
  end

  config.vm.define "node2" do |node|
    node.vm.box = "precise64"
    node.omnibus.chef_version = "12.4.1"

    node.vm.network "private_network", ip: "88.88.88.12"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "password" => "hocuspocus",
            "version" => "4.0.0",
            "memory_quota_mb" => 256,
            "package_full_url" => "http://packages.couchbase.com/releases/4.0.0/couchbase-server-community_4.0.0-ubuntu14.04_amd64.deb"
          }
        }
      }
    end
  end

  config.vm.define "node3" do |node|
    node.vm.box = "precise64"
    node.omnibus.chef_version = "12.4.1"

    node.vm.network "private_network", ip: "88.88.88.13"

    node.ssh.forward_agent = true
    node.ssh.forward_x11 = true

    node.vm.synced_folder ".", "/vagrant"

    node.vm.provision "chef_solo" do |chef|
      chef.cookbooks_path = ["bootstrap/cookbooks", "bootstrap/site-cookbooks"]
      chef.add_recipe "apt"
      chef.add_recipe "couchbase::server"
      chef.json = {
        "couchbase" => {
          "server" => {
            "password" => "hocuspocus",
            "version" => "4.0.0",
            "memory_quota_mb" => 256,
            "package_full_url" => "http://packages.couchbase.com/releases/4.0.0/couchbase-server-community_4.0.0-ubuntu14.04_amd64.deb"
          }
        }
      }
    end
  end
end
