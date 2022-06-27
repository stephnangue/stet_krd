pipeline {
  agent any

    stages {
        stage('Deploy to QA') {
            steps{
                echo "Deploying to QA"
            }
        }
        stage('QA Test') {
            parallel(
                'Quality': {
                    echo "Running Quality tests" 
                },
                'Functional': {
                    echo "Running Functional tests"
                },
                'Security': {
                    echo "Running Security tests"
                },
                'Performance': {
                    echo "Running Performance tests"
                }
            )
        }
        stage('KAL Validation') {
            parallel(
                'Quality': {
                    echo "Running Quality tests" 
                },
                'Functional': {
                    echo "Running Functional tests"
                },
                'Security': {
                    echo "Running Security tests"
                },
                'Performance': {
                    echo "Running Performance tests"
                }
            )
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
