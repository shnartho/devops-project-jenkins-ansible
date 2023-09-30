<h4>An Agile DevOps Project: Building a Jenkins CI/CD Pipeline with Ansible, Docker, GitHub Webhooks, and AWS✌️</h4>

#### Overview 

#### Servers Setup
1. EC2: To connect using aws ec2 instances, first check if "etc/ssh/sshd_config -> PasswordAuthentication yes", incase it is set to no then change it to yes otherwise using putty you cant connet to the ec2 instances. After that restart sshd
1. Jenkins: Install java runtime environment. For Jenkins installing follow https://www.jenkins.io/doc/book/installing/linux/. In jenkins pipeline, use source code git with github hook trigger and build step execute shell comand "scp -r /var/lib/jenkins/workspace/ansible-jenkins-pipeline/* root@{ip}:~/project/
ansible-playbook /var/lib/jenkins/playbooks/deployment.yaml"
3. Docker: For Docker installation follow https://docs.docker.com/engine/install/ubuntu/. After installing add user to docker group using "sudo usermod -aG docker $username" and refresh group using "newgrp docker" then you can use docker commands without error. Also to make sure ansible can ssh to docker server I need run "ssh-keygen", and then add ssh public key of ansible server from ~/.ssh/id_rsa.pub to the ~/.ssh/authorized_keys in docker server. Also set PermitRootLogin yes in sshd_config.
4. Ansible: For Ansible installation follow https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu. Then run "pip install docker". /etc/ansible/hosts and add servers "[Groupname] \nip of the servers"

#### Learnings
1. To run docker container in t2.micro aws, install "sudo apt-get install containerd", "sudo systemctl start containerd" and "sudo systemctl enable containerd"
