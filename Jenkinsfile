pipeline {
    agent any
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
        stage('downloading atifacts') {
            steps {
                 archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        stage('show test results') {
            steps {
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}