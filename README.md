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

This first time you do this, it needs to download the image which is ~2.5GB, so it might take a while. Subsequent
uses will use a locally stored version of the image and will be much quicker.

## Synced Source Files ##
In order to simplify development, this box provides a synced filesystem between files in the `src` 
directory of this git repository (i.e on the VirtualBox host) with `/home/cspace/custom_source` on the guest machine.
Any changes you make on the host will be relflected on the guest.

