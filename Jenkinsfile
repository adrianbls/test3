pipeline {
    agent any
     triggers {
        cron('H/5 * * * *') //Cada 5 minutos
    }
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
            when {
                anyOf {
                    changeset "src/**"
                }
            }
            steps {
                //sh "make build"
                //sh "make start"
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