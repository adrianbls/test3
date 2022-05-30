pipeline {
    /* specify nodes for executing */
    agent {
        label 'github-ci'
    }
 
    stages {
        /* checkout repo */
        stage('Checkout SCM') {                  Este es el primer stage
            steps {                              Con un único step, que lo que hace es conectarse al master del github
                checkout([                       en url, esta la url del repo
                 $class: 'GitSCM',
                 branches: [[name: 'master']],
                 userRemoteConfigs: [[
                    url: 'git@github.com:wshihadeh/rabbitmq_client.git',
                    credentialsId: '',
                 ]]
                ])
            }
        }
         stage('Do the deployment') {           Otro stage distinto
            steps {                             Con un solo step
                echo ">> Run deploy applications "
            }
        }
    }
 
    /* Cleanup workspace */
    post {
       always {
           deleteDir()
       }
   }
}