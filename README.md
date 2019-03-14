Ansible Essentials LAMP Demo
============================

This is the set of playbooks & roles used with the Ansible Essentials 'LAMP Demo'. The included files will allow you to (1. Vagrantfile) start three virtual machines using Vagrant; (2 hosts) list the three VMs in an Ansible inventory file, including connection info; (3 playbook.yml) run a single play playbook against a host as done in the webinar; (4 lamproles.yml) run a set of plays against multiple hosts using roles within a playbook.

### Requirements:
  - Vagrant
    + This will require a hypervisor to be installed, please check the [Vagrant documentation](https://www.vagrantup.com/docs/installation/ "Vagrant documentation") for more info.
  - [Ansible 2.7+](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html "Ansible") (The latest is recommended)
  - Sufficient CPU/RAM/disk to run multiple small VMs

  How to Use the Demo
  -------------------
### First:
This demo is meant to show Ansible performing some small-scale configuration in order to highlight its ease of use. These playbooks & roles are for demonstration only. You will find much more at https://galaxy.ansible.com/

1. **Download the repo.**
2. **Start the demo hosts**
    `$ vagrant up`
3. **Check basic connectivity to the hosts**
    `$ ansible -i hosts all -m ping`
4. **Output facts from the member group "Demo"**
    `$ ansible -i hosts demo -m setup`
5. **Display the drive information on your hosts**
    `$ ansible multi -i hosts -a "df -h"`
6. **Install the httpd web service with an ad-hoc command**
    `ansible -i hosts demo -m yum -a "name=httpd state=present" -b`
    **OR**
7. **Run the playbook.yml to perform more setup**
    `ansible-playbook -i hosts playbook.yml`
8. **Run the lamproles.yml playbook to install using roles**
    `ansible-playbook -i hosts lamproles.yml`

Visit th IP for the webserers group member in a web browser to verify the web app was installed.

**_Contributors:_**
@michelleperz (Michelle Perz)
@beeankha (Bianca Henderson)
@thedoubl3j (Jake Jackson)
@johnlieske (John Lieske)
