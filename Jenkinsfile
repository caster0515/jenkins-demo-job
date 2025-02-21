pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = ('server-credentials')
    }

    stages {
        stage('build') {
            steps {
                echo 'building'
                echo "building version ${NEW_VERSION}"
            }
        }
        stage('test') {
            steps {
        
                    echo 'building the application...'
            
                }
            }
        stage('deploy') {
            steps {
                    echo 'building the docker image...'
                    echo "${SERVER_CREDENTIALS}"
                    }
                }
            }
        }
