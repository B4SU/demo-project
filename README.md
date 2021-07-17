# demo-project

```jenkins
pipeline {
    agent any
        stages{
        stage('Clone GIT repo'){
            steps{
                git branch: 'main', url: 'https://github.com/B4SU/demo-project.git'
            }
        }

        stage('Run playbook'){
            steps{
                ansiblePlaybook credentialsId: 'hexact9', disableHostKeyChecking: true, installation: 'myansible', inventory: 'ansible/hosts', playbook: 'ansible/deploy-addressbook-kube.yml'
            }
        }
    }


}

```
