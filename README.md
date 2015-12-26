# ubuntu_bootstrap

## Initializing a desktop with fresh Ununtu 15.10
- Add NOPASSWD option to /etc/sudoers  
`sudo sed -i.bak -e 's/^%sudo  ALL=(ALL:ALL) ALL/%sudo   ALL=(ALL) NOPASSWD: ALL/' /etc/sudoers`
- Install Ansible 2 from [source](git@github.com:ansible/ansible.git)
```
sudo apt-get install -y git python-setuptools
git clone git@github.com:ansible/ansible.git
cd ansible
git submodule update --init --recursive
sudo -H python setup.py install
```
- Check out this repository and run ansible on its resipes
```
git clone git@github.com:flypunk/ubuntu_bootstrap.git
cd ubuntu_bootstrap
ansible-playbook basic_system_packages.yml
```
