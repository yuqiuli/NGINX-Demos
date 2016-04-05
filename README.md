# Misc NGINX Demos from conferences showing different functionality of NGINX and NGINX Plus

* **autoscaling-demo**: This demo uses one NGINX Plus instance as a load balancer with two upstream groups, one for NGINX Plus web servers and one for Elasticsearch nodes.  All of the instances run in Docker containers. The demo uses both the upstream_conf and status api's.  If shows creating a new NGINX Plus environment and adding and removing containers manually and with autoscaling.

* **consul-demo**: This demo spins up a bunch of docker containers and shows NGINX Plus being used in conjuction with Consul, a service discovery platform. It uses the upstream_conf API in NGINX Plus to add the servers registered with Consul and remove the ones which get deregistered without the need for reloading NGINX Plus. This automates the process of upstream reconfiguration in NGINX Plus based on Consul data using a simple bash script and Consul watches.

* **etcd-demo**: This demo spins up a bunch of docker containers and shows NGINX Plus being used in conjuction with etcd for service discovery. It uses the upstream_conf API in NGINX Plus to add the servers registered with etcd and remove the ones which get deregistered without the need for reloading NGINX Plus. This automates the process of upstream reconfiguration in NGINX Plus based on etcd data using a simple bash script and 'etcdctl exec-watch'.

* **mysql-galera-demo**: This demo uses NGINX Plus as a TCP load balancer for a MySQL Galera cluster consisting of two mysqld servers. It does round-robin load balancing between the 2 mysqld servers and also does active health checks using an xinetd script running on port 9200 inside each mysqld container.

* **random-files**: Demo to show random content and upstream_conf. Nick to add more description here

* **coreos-demo**: Shows how to use NGINX Plus to load balance an application running in a CoreOS cluster, 
utilizing *fleet* and *etcd*.

All of the Demos have been configured to utilize Vagrant and Ansible to enable autodeployment.

## Prerequisites for Vagrant/Ansible deploymnets

1. Install Vagrant using the necessary package for your OS:

       http://www.vagrantup.com/downloads

1. Install provider for vagrant to use to start VM's.

       The default provider is VirtualBox [Note that only VirtualBox versions 4.0, 4.1, 4.2, 4.3 are supported], which can be downloaded from the following link:

       https://www.virtualbox.org/wiki/Downloads

       A full list of providers can be found at the following page, if you do not want to use VirtualBox:

       https://docs.vagrantup.com/v2/providers/

1. Install Ansible:

       http://docs.ansible.com/ansible/intro_installation.html

1. Clone demo repo

       ```$ git clone git@github.com:nginxinc/NGINX-Demos.git```

1. Copy ```nginx-repo.key``` and ```nginx-repo.crt``` files for your account to ```~/NGINX-Demos/autoscaling-demo/ansible/files/```