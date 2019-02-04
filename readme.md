### Install Jenkins agent

This role intended for automated installation of Jenkins agent and configure it appropriately.

***OS tested and supported:***

| OS   | Tested  |
|---|---|
| Ubuntu 18  |  :white_check_mark: |
| Ubuntu 16  |  :white_check_mark: | 


***The role includes next steps:***

- Necessary packages installation to have ability to connect agent to Master node
- Docker installation
- Ansible container software installation and initial configuring

Docker is necessary to run builds inside containers.

[Ansible container](https://www.ansible.com/integrations/containers/ansible-container) software is necessary to install additional software and make configurational changes with ansible playbooks.

Ansible container config file is located in [repository](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_agents/container_settings/container.yml) and defines common settings for container.

Ansible role for the docker image configuring placed [here](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_agents/roles/manage_agent/tasks).

***How to make changes in base image:***
1. Add changes in ansible role mentioned before.
2. Run the Jenkins job [build_image](http://accelerator-automation.corp/job/build_image/) to build the image end place it on the agent node.


***To run playbook for agent installation:***
```
ansible-playbook jenkins_agents/install_agent.yml -i inventories/inventory
```


