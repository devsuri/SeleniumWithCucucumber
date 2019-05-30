pipeline {
    agent any
    
    stages {
        stage('validate'){
            try { 
                echo 'mvn validate'
                sh 'mvn validate'
                sshagent(['dev-pcmshoppingcart-app'])
            }
            finally
            {
                echo '[FAILURE] Failed to build'
                
              
                
            }}
        stage('compile'){
            try {
            echo 'mvn compile'
            sh 'mvn clean compile'
            }
            finally{
                echo '[FAILURE] Failed to build'
            }}
        
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
