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

For initial logon please use username and password, configured in file.

:warning: jenkins user from this file should be removed after personal user created for security reasons.


'''
ansible-playbook jenkins_master/install_jenkins_master.yml -i inventories/inventory
'''

