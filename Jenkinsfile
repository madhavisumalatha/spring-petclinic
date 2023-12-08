pipeline {
    agent any
    triggers { pollSCM('*/3 * * * *') }
    stages {
        stage('cloning spc code') {
            steps {
                git branch: 'main', url: 'https://github.com/madhavisumalatha/spring-petclinic.git'
            }
        }
        stage('Building and packaging') {
            steps {
                sh 'mvn package'
        
            }
        }
    }
}