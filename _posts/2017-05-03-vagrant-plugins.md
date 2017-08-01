---
layout: post
title: "Two Vagrant Plugins I Use"
tags: vagrant
---

The following two plugins enhance my Vagrant experience greatly. Perhaps you should also give them a try.

1. vagrant-vbguest
  - A Vagrant plugin to keep your VirtualBox Guest Additions up to date.
2. vagrant-proxyconf
  - Vagrant plugin that configures the virtual machine to use proxies.

## 1. Install
```
$ vagrant plugin install vagrant-vbguest
$ vagrant plugin install vagrant-proxyconf
```

## 2. Configuration 
### vagrant-vbguest
None.
### vagrant-proxyconf
Add the following lines in the Vagrantfile:
```
  if Vagrant.has_plugin?("vagrant-proxyconf")
    config.proxy.http     = "http://proxy.company.com:80"
    config.proxy.https    = "http://proxy.company.com:80"
    config.proxy.no_proxy = "localhost,127.0.0.1,.example.com"
  end
```

## 3. Start the VM
Now, you can start the VM with ```vagrant up```. :rocket:

## 4. Reference
1. <https://github.com/dotless-de/vagrant-vbguest>
2. <https://github.com/tmatilai/vagrant-proxyconf>
