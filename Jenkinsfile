pipeline {
    agent any
    stages {
        // Stage 1: Checkout code from GitHub
        stage('Checkout') {
            steps {
                git url: 'https://github.com/SherwinSatya/mern-backend', branch: 'main'
            }
        }

        // Stage 2: Install dependencies using npm
        stage('Install Dependencies') {
            steps {
                bat 'npm install' // For Windows, use 'bat'. For Linux/macOS, use 'sh'
            }
        }

        // Stage 3: SonarQube Analysis
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {  // Use the name of your SonarQube server configured in Jenkins
                    bat '''
                    C:/Users/Sherwin Satya Antony/Downloads/sonar-scanner-cli-6.2.1.4610-windows-x64/sonar-scanner-6.2.1.4610-windows-x64/bin/sonar-scanner -Dsonar.projectKey=mern- backend -Dsonar.sources=.
                    '''
                }
            }
        }
    }
}
