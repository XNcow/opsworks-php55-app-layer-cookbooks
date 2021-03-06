opsworks-php55-app-layer-cookbooks
==================================

AWS OpsWorks custom layer with support for PHP 5.5 and php application deployment. Also contains a centos 6.4 virtual machine using Vagrant.

Initial Setup
=============
1. Create a Stack with a custom cookbook pointing to `https://github.com/aporat/opsworks-php55-app-layer-cookbooks.git` (or clone this repo and host it yourself)
2. Pick chef version `11.10` as the chef version
3. Add a new `App Server -> PHP Layer` layer. Note that only Amazon Linux AMI is supported. 
4. Edit the newly created layer, and add the custom recipes:
  * add phpapp::configure & mysql::client in the setup lifetime event
  * add phpapp::deploy in the deploy lifetime event
5. Add a PHP application from the "Applications" section


Vagrant Setup
=============
1. Download Vagrant 1.5+ from http://www.vagrantup.com
2. Download VirtualBox from https://www.virtualbox.org
3. Install vagrant-omnibus `vagrant plugin install vagrant-omnibus`
4. Create a new project with the supplied `Vagrantfile` and edit `chef.cookbooks_path` to point to the cookbooks folder
