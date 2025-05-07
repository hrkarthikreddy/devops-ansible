# Installing Ansible by YUM or DNF
        1. sudo yum update -y
        2. sudo dnf install -y ansible-core 
        3. ansible --version

# OR

# Installing Ansible by python PIP module

##  Install as sudo user

        sudo python -m pip install ansible

##  Install ansible specific to a user

        python -m pip install --user ansible

##  Install ansible (minimal) specific to a user

        python -m pip install --user ansible-core
