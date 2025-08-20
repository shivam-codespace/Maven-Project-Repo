pipeline {
    agent any

     tools {
        maven "maven3"
     }


    environment {
         TOMCAT_HOME = "/home/anonymous/snap/tomcat11"
    }

    stages {
        stage('Build') {
            steps {
                 git branch: 'main', url: 'https://github.com/shivam-codespace/Maven-Project-Repo.git'
                 sh "mvn clean package"
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo "Deploying WAR to Tomcat..."
                 deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'f822a85e-36c0-42db-84e3-6278327ececc', path: '', url: 'http://localhost:8090')], contextPath: null, war: '**/*.war'
 
            }
        }
    }
}
