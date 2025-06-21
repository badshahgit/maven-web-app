pipeline {  

    agent any
        
    tools{
        maven "Maven-3.9.9"
    }
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/ashokitschool/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               sh 'mvn clean package'
            }
        }
        stage('docker image') {
            steps {
               sh 'docker build -t image .'
            }
        }
        stage('docker container') {
            steps {
               sh 'docker run -d -p 9090:8080 image'
            }
        }
    }
}
