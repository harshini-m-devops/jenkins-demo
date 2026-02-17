pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'chmod +x build.sh'
                sh './build.sh'
            }
        }
    }

    post {
        always {
            emailext(
                subject: "Build Status: ${currentBuild.currentResult}",
                body: "Build completed. Status: ${currentBuild.currentResult}",
                to: "harimar007@gmail.com"
            )
        }
    }
}

