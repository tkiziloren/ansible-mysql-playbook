# ansible-mysql-playbook

This is an example ansible playbook which
  - installs MySQL
  - creates a MySQL user named 'chembl'
  - creates a MySQL databased named 'chembl_24'
  - downloads and restores chembl_24 database dump (ftp://ftp.ebi.ac.uk/pub/databases/chembl/ChEMBLdb/latest/chembl_24_mysql.tar.gz)
  
## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites
Ansible should be installed in controller(master) machine
Tested in ubuntu server 16.04

### Installing

You can run this script in 3 steps:
```
git clone https://github.com/tkiziloren/ansible-mysql-playbook.git
cd ansible-mysql-playbook
ansible-playbook ebml.yml --extra-vars "ansible_become_pass=ANSIBLE_HOST_PASSWORD"
```
where **ANSIBLE_HOST_PASSWORD** is ssh password of your host machine.

### Testing the installation

**In the host machine** you can run the commands below to test installation.
```
mysql -u chembl -pchembl
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| **chembl_24**          |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
mysql> use chembl_24;
mysql> select * from action_type;
```
After the last command you should be able to see all actions in the action_types table;

## Improvements:
  - In current script if dump file is downloaded it doesn't try to download again. 
  - As an improvement it should control the checksum for the file in the checksums.txt and downloaded tar.gz file has different checksum from the remote file then it should be downloaded from the scratch.

## Authors
* **Tevfik Kiziloren** 

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

