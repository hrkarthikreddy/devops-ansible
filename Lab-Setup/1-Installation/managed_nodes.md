# Create ansible user on managed nodes

ssh opc@remote_server "sudo useradd ansible && sudo chown -R ansible:ansible /home/ansible"
ssh opc@remote_server "sudo mkdir -p /home/ansible/.ssh && sudo touch /home/ansible/.ssh/authorized_keys && sudo chown -R ansible:ansible /home/ansible/.ssh"
sudo cat id_rsa.pub | ssh opc@remote_server "ssh tee -a /home/ansible/.ssh/authorized_keys >/dev/null"
ssh opc@remote_server "sudo usermod -aG wheel,adm,systemd-journal ansible"