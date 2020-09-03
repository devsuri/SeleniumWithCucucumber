pipeline {
  agent any
  stages {
    stage('Test') {
      parallel {
        stage('Maven') {
          steps {
            echo 'Running from Jenkins file'
            sh(script: 'mvn compile', label: 'maven')
              #sh 'mvn clean compile'
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
