pipeline {
    agent any
 
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