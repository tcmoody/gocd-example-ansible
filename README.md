# gocd-example-ansible
Ansible for setting up a sample GoCD server+agent

Things to do to make this work:
1) Build out your dynamic ansible config per playbook for execution
2) Create+add a ssh key for source control, add that in to gocd-common/templates/ named github_temp_key
3) Grab autoregister key from cruiseconfig at /etc/go/cruiseconfig.xml for the the agent to autoregister.
4) Grab public ip for the env var for gocd_server_url in the go-agent-defaults file in gocd-agent/templates