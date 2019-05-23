pipeline {
    agent any
    
    stages {
        stage('validate'){
            steps { 
                echo 'mvn validate'
                sh 'mvn validate'
                gitCommit = sh(returnStdout: true, script: 'git rev-parse HEAD').trim()
                echo ${gitCommit}
                
            }}
        stage('compile'){
            steps {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }}
        }
}
