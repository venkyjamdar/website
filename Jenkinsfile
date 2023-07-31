pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Job1: Build
                git branch: ' ', url: 'https://github.com/ommaxyl/wbsite'
                sh 'docker build -t myfile /var/www/html'
            }
        }
        stage('Test') {
            when {
                anyOf {
                    branch 'master'
                    branch 'develop'
                }
            }
            steps {
                // Job2: Test
                sh 'docker run your-image-name npm test'
            }
        }
        stage('Deploy to Prod') {
            when {
                branch 'master'
            }
            steps {
                // Job3: Prod
                sh 'docker push your-image-name'
                // Add additional steps to deploy to production if needed
            }
        }
    }
}

