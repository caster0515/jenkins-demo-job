pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'exectueTests', defaultValue: true, description: '') 
    }

    stages {
        stage('build') {
            steps {
                echo 'building'
            }
        }
        stage('test') {

            when {
                expression {
                    params.exectueTests
                }
            }
            steps {
        
                    echo 'building the application...'
            
                }
            }
        stage('deploy') {
            steps {
                    echo 'building the docker image...'
                    }
                }
            }
        }
