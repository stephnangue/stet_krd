pipeline {
  agent any

    stages {
        stage('Deploy to QA') {
            steps{
                echo "Deploying to QA"
            }
        }
        stage('QA Test') {
            parallel {
                stage('Quality') {
                    echo "Running Quality tests" 
                }
                stage('Functional') {
                    echo "Running Functional tests"
                }
                stage('Security') {
                    echo "Running Security tests"
                }
                stage('Performance') {
                    echo "Running Performance tests"
                }
            }
        }
        stage('KAL Validation') {
            parallel {
                stage('Quality') {
                    echo "Running Quality tests" 
                }
                stage('Functional') {
                    echo "Running Functional tests"
                }
                stage('Security') {
                    echo "Running Security tests"
                }
                stage('Performance') {
                    echo "Running Performance tests"
                }
            }
        }
        stage('Review') {
            steps{
                echo "Reviewing the App"
            }          
        }
        stage('Release') {
            steps{
                echo "Releasing the App"
            }          
        }
    }
}
