pipeline {
    agent any
    
    stages {
        stage('validate'){
            steps { 
                echo 'mvn validate'
                sh 'mvn validate'
                
                echo ${gitCommit}
                
            }}
        stage('compile'){
            steps {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }}
        }
}
