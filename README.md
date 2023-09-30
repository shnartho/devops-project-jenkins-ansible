<h4>An Agile DevOps Project: Building a Jenkins CI/CD Pipeline with Ansible, Docker, GitHub Webhooks, and AWS✌️</h4>

#### Servers Setup
1. EC2: To connect using aws ec2 instances, first check if "etc/ssh/sshd_config -> PasswordAuthentication yes", incase it is set to no then change it to yes otherwise using putty you cant connet to the ec2 instances.
1. Jenkins: Install java runtime environment. For Jenkins installing follow https://www.jenkins.io/doc/book/installing/linux/
3. Docker: For Docker installation follow https://docs.docker.com/engine/install/ubuntu/. After installing add user to docker group using "sudo usermod -aG docker $username" and refresh group using "newgrp docker" then you can use docker commands without error.
4. Ansible: For Ansible installation follow https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu