# gitlab_vagrant_libvirt_ansible

Vagrant-libvirt setup that creates a VM and installs
[Gitlab CE](https://about.gitlab.com/install/?version=ce) using the official
packages.

Default OS is openSUSE Leap 15.6, but that can be changed in the Vagrantfile.
Please be aware, that this might break the Ansible provisioning.

## Vagrant

1. You need `vagrant`, obviously. And `git`. And Ansible...
1. Fetch the box, per default this is `opensuse/Leap-15.6.x86_64`, using
   `vagrant box add opensuse/Leap-15.6.x86_64`.
1. Make sure the git submodules are fully working by issuing
   `git submodule init && git submodule update`
1. Run `vagrant up`
1. Open the URL that Ansible printed out at the end of the provisioning. It
   should look something like `http://gitlab.192.0.2.13.sslip.io`. Use the
   credentials that were also printed out (`root` as the username and
   `atotallysecurepassword` as the password).
1. You can start playing around, create projects, change settings, etc. Please
   note that this setup does not configure mail providers, neither on the VM nor
   on the Gitlab level. So sending registration mails for new users etc. require
   that you configure things like SMTP yourself.
   Also, this setup does not setup a Gitlab runner VM. There is a separate
   vagrant setup called `gitlab_and_runner_vagrant_libvirt_ansible` for this.
1. Party!

## Cleaning up

The VM can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
