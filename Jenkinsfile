pipeline {
    agent any
    stages {
        stage (git) {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tomcat1', path: '', url: 'http://54.248.13.181:8081/')], contextPath: 'raju', war: '**/*.war'
            }
        }
    }
}
