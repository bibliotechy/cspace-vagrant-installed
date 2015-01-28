# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

  require 'rbconfig'
  def os
    @os ||= (
      host_os = RbConfig::CONFIG['host_os']
      case host_os
      when /mswin|msys|mingw|cygwin|bccwin|wince|emc/
        :windows
      when /darwin|mac os/
        :macosx
      when /linux/
        :linux
      when /solaris|bsd/
        :unix
      else
        raise Error, "unknown os: #{host_os.inspect}"
      end
    )
  end
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "cspace" do |app|
    app.vm.box = "cspace_4.2"
    app.vm.hostname = "vagrant.cspace-puppet.org"
    app.vm.box_url = "https://www.dropbox.com/s/yit1tnciy8z63rr/cspace_puppet_4.2.box?dl=1"
    app.vm.network :private_network, ip: "10.10.10.102"
    app.vm.network "forwarded_port", guest: 8180, host: 8180
    app.vm.provider "virtualbox" do |v|
      v.customize ["modifyvm", :id, "--memory", 3072]
        case os
        when /linux/
          v.customize ["modifyvm", :id, "--cpus", `grep "^processor" /proc/cpuinfo | wc -l`.chomp]
        when /macosx/
          v.customize ["modifyvm", :id, "--cpus", `sysctl -n hw.ncpu`.chomp]
        end
      end
    end

  #config.vm.synced_folder "src/", "/home/cspace/cspace_source/", owner: "cspace", group: "cspace"
end
