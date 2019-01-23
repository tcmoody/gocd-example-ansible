# gocd-example-ansible
Ansible for setting up a sample GoCD server+agent

Things to do to make this work:
1) Build out your dynamic ansible config per playbook for execution
2) Create+add a ssh key for source control, add that in to gocd-common/templates/ named github_temp_key
3) Grab autoregister key from the cruiseconfig on the server after provisioning at /etc/go/cruiseconfig.xml for the the agent to autoregister.
4) Grab public ip for the env var for gocd_server_url in the go-agent-defaults file in gocd-agent/templates.

Example Commands:
EC2_INI_PATH=ec2-private.ini AWS_PROFILE=gocd-example ANSIBLE_SSH_ARGS="-F dynamic_ansible_ssh.cfg -o ControlMaster=auto -o ControlPersist=30m" ansible-playbook playbooks/gocd_server.yml -i ec2.py

EC2_INI_PATH=ec2-private.ini AWS_PROFILE=gocd-example ANSIBLE_SSH_ARGS="-F dynamic_ansible_ssh.cfg -o ControlMaster=auto -o ControlPersist=30m" ansible-playbook playbooks/gocd_agent.yml -i ec2.py

PROVISION THE SERVER FIRST.
