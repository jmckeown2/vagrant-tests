# vagrant-tests

Vagrant tests is here just to compare how VirtualBox managed by Vagrant performs on a given host

## Pre-test Configuration
Download and install current versions of [VirtualBox](https://www.virtualbox.org/wiki/Downloads) 
and [Vagrant](https://www.vagrantup.com/downloads)

The pre-test configuration ensures the Box file has been downloaded from the internet, and is ready for use by Vagrant it does this by creating and immediately destroying a vm. 

```bash
vagrant up && vagrant destroy -f
```

## `vagrant up` with provisioning

```bash
time vagrant up
```

Assuming this is run after a destroy, Vagrant needs to import the VM, before booting, and running any provisioning scripts. The `time` commmand will report the time it took the shell to run the `vagrant up` command while the `Vagrantfile` itself reports it's internal timeing. Note both how long it took and any discrepencies between the two values reported.

```text
==> default: Running action triggers after up ...
==> default: Running trigger...
Vagrant trigger config duration = 40.59736204147339

real	0m41.112s
user	0m4.161s
sys	    0m2.328s
```
**Note** The internal duration and the shell's real values are < 1s different.
