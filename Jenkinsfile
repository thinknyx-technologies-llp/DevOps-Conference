pipeline {
    agent any
    
    tools{
        maven 'mvn_home'
    }

    stages {
        
        stage ('Static Scan'){
            steps {
                withMaven(maven : 'mvn_home') {
                    bat 'mvn verify sonar:sonar -Dsonar.projectKey=devops-conference -Dsonar.organization=kmayer10 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=1c413160ec451fe75e316d376b1646e73a992176'
                }
            }
        }
        
        stage ('Compile Stage') {
            steps {
                withMaven(maven : 'mvn_home') {
                    bat 'mvn clean install'
                }
            }
        }
    }
}
