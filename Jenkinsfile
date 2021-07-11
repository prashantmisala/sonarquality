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
            sh 'mvn sonar:sonar'
            }
       }
      stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
            }
          }
       }    
   }  
     
    

