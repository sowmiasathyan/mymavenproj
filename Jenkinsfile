pipeline {
    agent any
    tools {
        maven 'maven3.81'
    }
    stages {
        stage('Get the code') {
            steps {
                git 'https://github.com/sowmiasathyan/mymavenproj'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Approval from release manager') {
            input {
                message "Approved By ReleaseManager"
            }
            steps {
                sh 'echo "hello"'
            }
        }
        stage('DevDeploy') {
            steps {
                sh 'cp target/JenkinsWar.war /var/lib/tomcat9/webapps'
            }
        }
    }
}
