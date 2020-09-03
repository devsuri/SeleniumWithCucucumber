#pipeline {
#    agent any
    
#stages{
#    stage('Build') {
#        steps{
 #            
#                sh 'mvn clean compile'
#                 
#               }
#         }
#         
#        }
#}

pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Maven') {
          steps {
            echo 'Running from Jenkins file'
            sh(script: 'mvn compile', label: 'maven')
          }
        }

        stage('Cucumber') {
          steps {
            cucumber '**/*.json'
          }
        }

      }
    }

  }
}
