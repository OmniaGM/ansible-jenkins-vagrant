Provisioning Jenkins using Ansible and Vagrant
==============================================

This repo is based on [bertvv/ansible-skeleton](https://github.com/bertvv/ansible-skeleton)

Installation
------------

On the management node, make sure you have installed recent versions of:

-	[VirtualBox](https://virtualbox.org/)
-	[Vagrant](https://vagrantup.com/)
-	[Git](https://git-scm.com/) and for Windows hosts also Git Bash. If you install Git with default settings (i.e. always click "Next" in the installer), you should be fine.
-	Ansible (only on Mac/Linux)

You can either clone this project or use the provided initialization script.

When cloning, choose another name for the target directory!

```ShellSession
$ git clone git@github.com:OmniaGM/ansible-jenkins-vagrant.git my-jenkins
```

On Windows, it is important to keep line endings in the Linux format:

```ShellSession
$ git clone --config core.autocrlf=input https://github.com/OmniaGM/ansible-jenkins-vagrant.git my-jenkins
```

Getting started
---------------

1.	modify jenkins_new_user and jenkins_new_user_pass you need to use it for jenkins in `group_vars/all.yml`

2.	add more jobs for your jenkins in `pipeline/files/jobs`

3.	`jenkins-provision` job, will re-provission jenkins again with every push

If you which to update jenkins version or add more plugins then you can modify `ansible/roles/jenkins/vars/main.yml` to select your favourite jenkins version or your plugin

Build jenkins using vagrant
---------------------------

```
vagrant up
```

Build jenkins locally
---------------------

```
./scripts/run-playbook-locally.sh
```

Then go to `https:127.0.0.1:8080` with your jenkins new user credentials
