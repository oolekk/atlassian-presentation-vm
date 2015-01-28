# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

	config.vm.provider "docker" do |d|
		d.force_host_vm = true
		d.vagrant_vagrantfile = "./host/Vagrantfile"
	end

	config.vm.define "jira" do |v|
		v.vm.provider "docker" do |d|
			d.image = "nkatsaros/atlassian-jira"
			d.name = "my-jira"
			d.ports = ["8080:8080"]
		end
	end

	config.vm.define "stash" do |v|
		v.vm.provider "docker" do |d|
			d.image = "nkatsaros/atlassian-stash"
			d.name = "my-stash"
			d.ports = ["7990:7990", "7999:7999"]
		end
	end

	config.vm.define "bamboo" do |v|
		v.vm.provider "docker" do |d|
			d.image = "nkatsaros/atlassian-bamboo"
			d.name = "my-bamboo"
			d.ports = ["8085:8085", "54663:54663"]
		end
	end

end
