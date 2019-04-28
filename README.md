# Aridnik-CICD-Ansible
##### Sample ansbile playbooks for jenkins, nexus, tomcat setup and deployments

## Playbooks
  - setup.yml
  - deploy.yml
  
## Inventory
  - dev
  - qa
  - staging
  - prod
  - all
  
## Roles
  - set-facts
  - common-tools
  - java8-setup
  - tomcat8-setup
  - jenkins-setup
  - nexus-setup
  - deploy

```sh
# Clone cicd-ansible repository
$ git clone https://github.com/aridnik/cicd-ansible.git
$ cd cicd-ansible

# infra setup
$ ansible-playbook -i inventory/all setup.yml 

# deployment on dev
$ ansible-playbook -i inventory/dev deploy.yml -e "env=dev CODE_VERSION=YYYY.MM.BUILD_NUMBER-SNAPSHOT"

# deployment on qa
$ ansible-playbook -i inventory/dev deploy.yml -e "env=qa CODE_VERSION=YYYY.MM.BUILD_NUMBER-SNAPSHOT"

# deployment on staging
$ ansible-playbook -i inventory/dev deploy.yml -e "env=staging CODE_VERSION=YYYY.MM.BUILD_NUMBER-SNAPSHOT"

# deployment on prod
$ ansible-playbook -i inventory/dev deploy.yml -e "env=prod CODE_VERSION=YYYY.MM"
```
