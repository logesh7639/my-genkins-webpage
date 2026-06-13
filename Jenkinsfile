pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/logesh7639/my-jenkins-webpage.git',
                    credentialsId: 'your-jenkins-credential-id'
            }
        }
        stage('Deploy to S3') {
            steps {
                sh '''
                aws s3 sync . s3://jenkins-webpage-bucket --delete
                '''
            }
        }
    }
}
