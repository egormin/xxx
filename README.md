### Install Jenkins master

This role intended to automated installation of Jenkins master server.

***OS tested and supported:***

| OS   | Tested  |
|---|---|
| Ubuntu 18  |  :white_check_mark: |
| Ubuntu 16  |  :white_check_mark: | 

| ***Jenkins Ver.***|
|---|
| ***2.162***  | 

***The role includes next steps:***

- Jenkins server installation
- Jenkins temporary user for automated configuration creation
- Initial configuration
- Plugins installation
- Port redirection configuring with nginx

For initial logon please use username and password, configured in [file](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master/roles/jenkins_master/defaults/main.yml?at=wip_develop).

:warning: **jenkins user from this file must be removed after personal user creating for security reasons** :warning: 

The version of Jenkins can be configured in [file](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master/roles/jenkins_master/vars/main.yml?at=refs%2Fheads%2Fwip_develop)

***To run playbook:***
```
ansible-playbook jenkins_master/install_jenkins_master.yml -i inventories/inventory
```

***How to manage Jenkins service***

Since Jenkins is configured as a service it can be managed with stadard systemctl commands:
```
systemctl stop jenkins
systemctl status jenkins
systemctl start jenkins
systemctl restart jenkins
```

***Jenkins update***

To update Jenkins instance to new version:
```
apt-get update
apt-get install jenkins
```

