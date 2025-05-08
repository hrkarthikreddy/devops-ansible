# Installing Ansible by YUM or DNF

        sudo dnf install epel-release
        sudo dnf update
        sudo dnf install ansible
        ansible --version

# OR

# Installing Ansible by python PIP module

## Install pip for python
        sudo yum install python3-pip
        python3 -m pip install --upgrade pip

##  Install as sudo user

        sudo python3 -m pip install ansible

##  Install ansible specific to a user

        python3 -m pip install --user ansible

##  Install ansible (minimal) specific to a user

        python3 -m pip install --user ansible-core
