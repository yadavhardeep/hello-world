pipeline {
    agent any
    tools {
        maven 'apache-maven-3.6.0'
    }
    parameters {
        string(name:'person', defaultValue:'Hardeep Yadav', description:'pipeline executor!!!!')
    }
    stages {
        stage('Build'){
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "${params.person}"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Yadav', description: 'Who should I say hello to?')
                }
            }
            steps{
                echo "Hello ${params.person}"
                bat 'mvn --version'
                echo 'hello ! Pipeline is in build stage !!!!!!!!!!'
            }
            
        }
        stage('Test'){
            steps{
                echo 'hello ! Pipeline is in test stage !!!!!!!!!!'    
            }
        }
        stage('deploy'){
            steps{
                echo 'hello ! Pipeline is in deploy stage !!!!!!!!!!'    
            }
        }
        stage('demo'){
            steps{
                echo pwd()    
            }
        }
    }
    post {
        success {
            echo 'PIPELINE EXECUTED SUCCESSFULLY !!!!'
        }
        
        failure {
            echo 'PIPELINE EXECUTION FAILED !!!!'
        }
    }
}
