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
        sh '''
        sudo cp target/ROOT.war /opt/tomcat/webapps/
        sudo chmod 755 /opt/tomcat/webapps/ROOT.war
        sudo systemctl restart tomcat
        '''
    }
}
        }
    }
}
