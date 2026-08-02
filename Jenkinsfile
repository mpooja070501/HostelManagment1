pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Git Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/mpooja070501/HostelManagment1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh '''
                cp target/HostelManagementSystem.war /opt/tomcat/webapps/
                '''
            }
        }
    }

    post {
        success {
            echo 'Deployment Successful!'
        }
        failure {
            echo 'Deployment Failed!'
        }
    }
}
