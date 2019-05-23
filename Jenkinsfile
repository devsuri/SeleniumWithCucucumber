pipeline {
    agent any
    echo env.GIT_COMMIT
    echo env.GIT_BRANCH
    stages {
        stage('validate'){
            steps { 
                echo 'mvn validate'
                sh 'mvn validate'
            }}
        stage('compile'){
            steps {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }}
        }
}
