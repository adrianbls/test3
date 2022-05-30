pipeline {
    agent any
 
    stages {
        stage('Checkout GITHUB') {
            steps {
                checkout([
                 $class: 'GitSCM',
                 branches: [[name: 'main']],
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