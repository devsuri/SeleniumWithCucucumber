pipeline {
    agent any
    
    stages {
        stage('validate'){
            steps { 
                echo 'mvn validate'
                sh 'mvn validate'
                sh 'echo ${env.GIT_COMMIT}'
                sh 'echo ${env.GIT_BRANCH}'
                
            }}
        stage('compile'){
            steps {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }}
        }
}
