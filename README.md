#CollectionSpace Vagrant built on an image with collectionspace preinstalled#

##Dependencies##

* [VirtualBox](https://www.virtualbox.org/manual/ch02.html)
* [Vagrant](https://www.vagrantup.com/downloads)

##Get started##

```
git clone https://github.com/bibliotechy/cspace-vagrant-installed

cd cspace-vagrant-installed

vagrant up
```

This first time you do this, it needs to download [the image](https://www.dropbox.com/s/yit1tnciy8z63rr/cspace_puppet_4.2.box?dl=1) which is ~2.5GB, so it might take a while. Subsequent
uses will use a locally stored version of the image and will be much quicker.
Alternatively, you can download the image before you run `vagrant up` and then run:

`vagrant box add cspace_4.2 /path/to/downloaded/cspace_puppet_4.2.box`


## Synced Source Files ##
In order to simplify development, this box provides a synced filesystem between files in the `src` 
directory of this git repository (i.e on the VirtualBox host) with `/home/cspace/custom_cspace_source` on the guest machine.
Any changes you make on the host will be relflected on the guest.

