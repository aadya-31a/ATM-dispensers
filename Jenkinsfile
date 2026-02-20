pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Build running..."
            }
        }
    }

    post {
        success {
            emailext (
                to: 'maneesha9391@gmail.com',
                subject: "SUCCESS: ${env.JOB_NAME} Build #${env.BUILD_NUMBER}",
                body: """
                ✅ Build Successful

                Job Name: ${env.JOB_NAME}
                Build Number: ${env.BUILD_NUMBER}
                Status: SUCCESS
                Build URL: ${env.BUILD_URL}

                Please check attached build log.
                """,
                attachLog: true,
            )
        }
    }
}
