# Objective: Ping Remote hosts to test connectivity

###### open file /etc/ansible/host
###### make host entry
        Syntax:username@ip/hostname
        ansible@10.10.2.134
###### ping the host
        ansible -m ping all
