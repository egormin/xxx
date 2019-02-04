### Jenkins master and agents automated installation

Folder [jenkins_master](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_master) contains files for Jenkins master installation.

Folder [jenkins_agents](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/jenkins_agents) contains files for Jenkins agents installation and management.

Folder [inventories](https://stash.playtika.com/projects/JB/repos/jenkins_automation/browse/inventories) contains common inventory information.

The provided solution implies the immutable approach for the builds. The jobs are going to be runned inside a container based on the base docker image. For that docker service is installed on the agent. The benefits of this approach:
- The container runs only during job live time
- Every job runs own separate container independent from each other
- Every change performed during that build dischardes when container stops
- Base image is a singe point for changes and configuration
- Every build has the same isolated environment 
- Ability tp make same changes like software installation and configuration inside a container without any fluence on other containers
