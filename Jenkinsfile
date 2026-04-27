pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout Code') {
    steps {
        git branch: 'main',
            url: 'https://github.com/kajal-patel1106/MiniProject_Devops.git'
    }
}

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [
                    tomcat10(
                        credentialsId: 'tomcat-cred',
                        path: '',
                        url: 'http://35.154.144.83:8080'
                    )
                ],
                contextPath: '',
                war: 'ROOT.war'
            }
        }
    }
}
