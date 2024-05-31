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
        always {
            script {
                sh """
                echo "Check console output at ${BUILD_URL} to view the results." | /usr/bin/mail -s "Jenkins Build #${BUILD_NUMBER} - ${currentBuild.currentResult}" vgprabu17@gmail.com
                """
            }
        }
    }
}