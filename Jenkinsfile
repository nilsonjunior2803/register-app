pipeline {
    agent any
    environment {
              APP_NAME = "register-app-pipeline"
    }

    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }

        stage("Checkout from SCM") {
               steps {
                   git branch: 'main', credentialsId: 'github', url: 'https://github.com/nilsonjunior2803/register-app'
               }
        }

        stage("Build Application") {
                 steps {
                     sh "mvn clean package"
                 }
          }
  
        stage("Test Application") {
                 steps {
                     sh "mvn test"
                 }
          }
    }
}