pipeline {
    agent any
    
    tools{
        maven 'mvn_home'
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
