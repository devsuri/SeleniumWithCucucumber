pipeline {
    agent any
    options {
    buildDiscarder(logRotator(numToKeepStr: '3'))
}
    tools {
    maven 'M2_HOME'
  }
    stages {
        stage('validate'){
            steps { 
                //echo 'mvn validate'
                //sh 'mvn validate'
            sh 'mvn -B -DskipTests clean package'
            }}
        stage('compile'){
            steps {
            echo 'mvn compile'
            //sh 'mvn clean compile'
            }}
        }
}
