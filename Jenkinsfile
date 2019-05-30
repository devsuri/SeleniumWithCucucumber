pipeline {
    agent any
    
    stages {
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
}
