pipeline {
    agent any
    
    tools{
        maven 'mvn_home'
    }

    stages {
        
        
        
        stage ('Packaging and Distribution') {
            steps {
                withMaven(maven : 'mvn_home') {
                    sh 'mvn clean deploy'
                }
            }
        }
        
        stage ('Getting List of hosts for deployment') {
            steps {
                copyArtifacts filter: 'hosts', projectName: 'System Provisioning', target: '.'
            }
        }
        
        stage ('Deploying Application on Test Environment') {
            steps {
                sh 'ansible-playbook deployment.yml -i hosts'
            }
        }
    }
}
