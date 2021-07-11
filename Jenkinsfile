pipeline {
    agent any
    stages {
        stage('compile') { 
            steps {
            echo 'compile'
            sh 'mvn compile'
            }
        }
        stage('package') { 
            steps {
            echo 'package'
            sh 'mvn package'
            }
        }
        stage('testing') {
            steps {
            echo 'package'
            sh 'mvn sonar:sonar -Dsonar.host.url=http://34.231.242.10:9000 -Dsonar.login=d9716ed2d72b2f7281638a3b20cf5d1c859e2f1a'
            }
       }
       stage('deploy') {
            steps {
            sh 'mvn deploy'
            }
        }
    }    
 }  
     
    

