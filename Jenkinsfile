pipeline {
    agent any
    stages {
        stage('Welcome') { 
            steps {
                echo 'Hi , You are inside the pipeline'
            }
        }
        stage('build') {
            steps {
                script {
                    docker.build('hello-world-app')
                }
            }
        }
    }
    post {
    success {
      mail to: vgprabu17@gmail.com, subject: ‘The Pipeline success :(‘
    }
  }
}