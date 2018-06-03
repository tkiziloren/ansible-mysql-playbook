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

You can run this script in three steps
```
git clone https://github.com/tkiziloren/ansible-mysql-playbook.git
cd ansible-mysql-playbook
ansible-playbook ebml.yml --extra-vars "ansible_become_pass=ANSIBLE_HOST_PASSWORD"
```
## Authors

* **Tevfik Kiziloren** 

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

