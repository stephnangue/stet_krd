pipeline {
    agent any
    parameters {
        string(name: 'SABR_MOTEUR_VERSION', defaultValue: '1.1.1', description: 'Version du moteur SABr')

        string(name: 'SABR_IHM_VERSION', defaultValue: '2.2.2', description: 'Version de SABr IHM')

        string(name: 'SIMULATEUR_VERSION', defaultValue: '3.3.3', description: 'Version du simulateur SABr')
    }
    stages {
        stage('Deploy to QA') {
            steps{
              echo "Hello ${params.SABR_MOTEUR_VERSION}"
              
              echo "Hello ${params.SABR_IHM_VERSION}"
              
              echo "Hello ${params.SIMULATEUR_VERSION}"
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
