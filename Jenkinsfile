pipeline {
    /* specify nodes for executing */
    agent {
        label 'github-ci'
    }
 
    stages {
        stage('Checkout GIT') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'master']],
                 userRemoteConfigs: [[url: 'https://github.com/adrianbls/Test_jenkins.git']]
                ])
            }
        }
         stage('Deployment') {
            steps {
                echo ">> Ejecutar Deploy "
            }
        }
    }

    post {
       always {
           deleteDir()
       }
   }
}