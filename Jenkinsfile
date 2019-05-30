pipeline {
    agent any
    
  /*  stages {
        stage('validate'){
            sstep { 
                echo 'mvn validate'
                sh 'mvn validate'
                
            }
            }
        stage('compile'){
           step {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }
            }
        
        stage('DeployToDevelopment') {

              

                steps {
                    echo 'Deploying to Development Environment'
               //sshagent(['dev-pcmshoppingcart-app']) {


            // sh 'ssh -o StrictHostKeyChecking=no '${env.deploy}''
             sh "scp -r $WORKSPACE/tpls/* '${env.deploy}':'/usr/bin/'"

            //}
        }
        }
        }
}*/

stages{
    stage('Build') {
        steps{
             catchError {
                sh 'mvn clean compile'
                 sshagent(['dev-pcmshoppingcart-app'])
               }
         }
         post {
            success {
                echo 'Build stage successful'
            }
            failure {
                echo 'Compile stage failed'
                error('Build is aborted due to failure of build stage')

             }
    }
   }
  stage ('Production'){
        steps {
                echo 'Deploying to Development Environment'       
              }
        }
}}
