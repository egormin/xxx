### Install Jenkins master

This role intended to automated installation of Jenkins master server.

***OS tested and supported:***

| OS   | Tested  |
|---|---|
| Ubuntu 18  |  :white_check_mark: |
| Ubuntu 16  |  :white_check_mark: | 

***The role includes next steps:***

- Jenkins server installation
- Jenkins temporary user for automated configuration creation
- Initial configuration
- Plugins installation
- Port redirection configuring with nginx

For initial logon please use username and password, configured in [file](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master/roles/jenkins_master/defaults/main.yml?at=wip_develop).

:warning: jenkins user from this file ьгые be removed after personal user creating for security reasons.

The version of Jenkins can be configured in [file](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master/roles/jenkins_master/vars/main.yml?at=refs%2Fheads%2Fwip_develop)

Currently configured for installation version: ***2.162***

***To run playbook:***
```
ansible-playbook jenkins_master/install_jenkins_master.yml -i inventories/inventory
```

