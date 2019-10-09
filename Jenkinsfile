pipeline {
    agent any
    
    tools{
        maven 'mvn_home'
        jdk 'java 8'
    }

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'mvn_home') {
                    bat 'mvn clean install'
                }
            }
        }
    }
}
