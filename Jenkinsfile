pipeline {
  agent any

    stages {
        stage('Deploy to QA') {
            steps{
              echo "SABR_MOTEUR_VERSION = ${SABR_MOTEUR_VERSION}"
              echo "SABR_IHM_VERSION = ${SABR_IHM_VERSION}"
              echo "SIMULATEUR_VERSION = ${SIMULATEUR_VERSION}"
            }
        }
        stage('QA Test') {
            parallel {
                stage('Quality') {
                    steps{
                        echo "Running Quality tests"
                    }
                }
                stage('Functional') {
                    steps{
                        echo "Running Functional tests"
                    }                  
                }
                stage('Security') {
                    steps{
                         echo "Running Security tests"
                    }                      
                }
                stage('Performance') {
                    steps{
                         echo "Running Performance tests"
                    }                   
                }
            }
        }
        stage('Deploy to KAL') {
            steps{
                echo "Deploying to KAL"
            }
        }
        stage('KAL Validation') {
             parallel {
                stage('Quality') {
                    steps{
                        echo "Running Quality tests"
                    }
                }
                stage('Functional') {
                    steps{
                        echo "Running Functional tests"
                    }                  
                }
                stage('Security') {
                    steps{
                         echo "Running Security tests"
                    }                      
                }
                stage('Performance') {
                    steps{
                         echo "Running Performance tests"
                    }                   
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
