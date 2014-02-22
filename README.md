![image](https://f.cloud.github.com/assets/2453394/2131655/75d3d610-92a3-11e3-977c-44a3cb6ec8c0.png)

This repository is for the S.S. Failboat, a local development environment maintained by Captain Horace, the Dragon Daddy (aka @mdwheele).

## Features

### Installed Packages

* PHP 5.3.3
* MySQL 5.1
* Apache 2.2
* phpMyAdmin (Latest Stable)
* Git 1.7


## Running the Environment

This is a [Vagrant](http://www.vagrantup.com/) development environment.  Vagrant is a command-line wrapper around [VirtualBox](https://www.virtualbox.org) and must be installed to use the environment.  Installation instructions for Vagrant can be found below:

- [Installing Vagrant](http://docs.vagrantup.com/v2/installation/index.html)

### Cloning the Repository

After installing Vagrant, you can clone this repository anywhere you choose.  The Vagrant configuration mounts a directory on the host system into the virtualized environment for Apache to serve so you will not be doing development inside this repo.  It can go anywhere!

**Clone this repository somewhere nice and fluffy!**

The following command will clone the repository to your current working directory:

```> git clone git@github.com:mdwheele/failboat.git```

**Change directories into the cloned repository.**

In order to start any vagrant environment, you must be inside the directory where a `Vagrantfile` is specified.

**Start the environment.**

This step will take a significant amount of time to execute the first time you run it.  During a first start of this environment, the following operations will happen:

1. A [CentOS 6.5 Virtual Machine](http://puppet-vagrant-boxes.puppetlabs.com/centos-65-x64-virtualbox-puppet.box) will be downloaded, imported, configured, and booted into VirtualBox.
2. Core utilities will be provisioned.  This includes things like Yum repositories, `gcc`, `vim`, `git`, etc.
3. A LAMP Stack is provisioned.
4. Developer utilities are installed.  This includes things like phpMyAdmin, PHPUnit, Guard, Grunt, a SASS compiler, etc.

So, all that said, it takes about 8-10 minutes to provision on a circa 2010 Macbook Pro.  Just let it do its thang' and **do not stop it whatever you do**!

*Starting the environment*

	> vagrant up
	
*Logging into the VM*

	> vagrant ssh
	
*Stopping the environment*

	> vagrant halt
	
*Destroying the environment*

	> vagrant destroy
	
## Usage

### Running commands with `root` permissions

You shouldn't need to do this often, but if you ever want to test-drive a package that isn't installed, it may be necessary.  In the case that you do find that something is not installed in the environment by default, please create an issue so that it may be considered.  

The `vagrant` user is, by default, added to `/etc/sudoers`.  To execute a command with `root` permissions, do as follows:

	> sudo vi /etc/hosts  

This would open `/etc/hosts` using the `vi` text editor with `root` permissions.

## Development

### Contributing

Contributions are **welcome** and will be fully **credited**.  Contributions via Pull Requests are accepted on [Github](https://github/mdwheele/failboat).  

#### Pull Requests

- **Document any change in behaviour** - Make sure the README and any other relevant documentation are kept up-to-date.

- **Create topic branches** - Don't ask us to pull from your master branch.

- **One pull request per feature** - If you want to do more than one thing, send multiple pull requests.

- **Send coherent history** - Make sure each individual commit in your pull request is meaningful. If you had to make multiple intermediate commits while developing, please squash them before submitting.
