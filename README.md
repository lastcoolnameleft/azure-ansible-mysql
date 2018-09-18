# Azure Deployment of MySQL + MHA with Ansible

This repo is based off of the following Azure Quickstart Template for MHA Proxy via Ansible (instead of ARM template)

https://github.com/Azure/azure-quickstart-templates/tree/master/mysql-mha-haproxy-ubuntu

## Infrastructure 

The following infrastructure resources are created by the vm.yaml and network.yaml Ansible playbooks:

* Vnet
  * Subnet
  * Security Group
* VM's
  * 2 MySQL Masters
  * 2 MySQL Agents
  * 1 HAProxy + MHA Master

## Deployment

The following installation steps are followed by the mha-setup.yaml and mysql-setup.yaml Ansible playbooks:

* Install MySQL on each MySQL VM
* Setup MySQL replication between the MySQL Master master and the MySQL agents
* Install MHA on each MySQL + HA
* Setup MHA for replication failover
