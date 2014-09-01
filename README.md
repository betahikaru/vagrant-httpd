vagrant-httpd
=============

This is sandbox for httpd by vagrant.

# Require
- OSX 10.9.4 or later
- Vagrant 1.6.3 or later
- Virtual Box 4.3.6 or later

# Usage
Run command bellow.

```shell
git clone git@github.com:betahikaru/vagrant-httpd.git
cd vagrant-httpd
vagrant up
open http://localhost:8081/
```

Edit ```./data``` as DocumentRoot directory. This directory has index.html and enchant.js and some image for a charactor.
When you edit file, run ```vagrant provision``` command. Then DocumentRoot directory is refresh by vagrant provisioning process defined by shellscript in Vagrant file.


# Licence
MIT

