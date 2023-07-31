pipeline {
    agent any

    stages {
        stage('Job2') {
            when {
                // Only trigger this stage if the commit is made to the develop branch
                branch 'develop'
            }
            steps {
                // Add the test steps here
                // For example: sh 'npm test' or 'mvn test', depending on your project
            }
        }
        stage('Job2 and Job3') {
            when {
                // Only trigger this stage if the commit is made to the master branch
                branch 'master'
            }
            steps {
                // Add the test steps here
                // For example: sh 'npm test' or 'mvn test', depending on your project

                // Add the production deployment steps here
                // For example: sh 'npm run deploy' or 'mvn deploy', depending on your project
                // Note: Be cautious with production deployments, ensure you have proper safeguards.
            }
        }
    }
}

