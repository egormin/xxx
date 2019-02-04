### Jenkins master and agents automated installation

#### Jobs inside a docker container approach
The provided solution implies the immutable approach for the builds. The jobs are going to be run inside a container based on the base docker image. For that docker service is installed on the agent. The benefits of this approach:
- The container runs only during job live time
- Every job runs in own separate container, independent from each other
- Every change, performed during that build, will discharge when container stops
- The base image is a single point for changes and configuration
- Every build has the same isolated environment 
- Ability to make some changes, like software installation and configuration, inside a container without any influence on other containers

#### Build image approach
[Ansible contained tool](https://www.ansible.com/integrations/containers/ansible-container) was applied for the docker image build process and it allows to define the list of software for installation and necessary configuration with ansible code.

#### How to run job inside a container
```
    
node {
    withDockerContainer('jenkins-build_agent') {
        stage ("First stage") {
            sh('some commands')
        }
         stage ("Second stage") {
            sh('some commands')
        }
    }
}
```
here `jenkins-build_agent` is the name of base image.


Folder [jenkins_master](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master) contains files for Jenkins master installation.

Folder [jenkins_agents](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_agents) contains files for Jenkins agents installation and management.

Folder [inventories](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/inventories) contains common inventory information.
