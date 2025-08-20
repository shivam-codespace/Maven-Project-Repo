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
    }
}
