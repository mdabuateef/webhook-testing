pipeline {
    agent any

    triggers {
        // Polls GitHub for changes in the repository
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh 'cp target/HelloWorldApp-1.0-SNAPSHOT.war /opt/tomcat/webapps/'
            }
        }
    }
}
