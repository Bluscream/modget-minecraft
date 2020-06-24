pipeline {
    agent {
        docker {
            image 'openjdk:8-jdk'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh './gradlew build'
            }
            post {
                success {
                    archiveArtifacts artifacts: 'build/libs/*', fingerprint: true
                }
            }
        }
    }
}
