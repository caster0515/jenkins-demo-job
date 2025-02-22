pipeline {
    agent any
    tools {
       maven 'maven-3.9' 
    }
    
    stages {
        stage('build jar') {
            steps {
                script {
                   echo 'building the application..'
                   sh 'mv package'
                }
            }
        }

            stage('build image') {
            steps {
                script {
                   echo 'building the docker image..'
                   withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                      sh 'docker build -t caster0515/demo-app:jma-2.0 .'
                      sh 'echo $PAS | docker login -u $USER --password-stdin'
                      sh 'docker push caster0515/demo-app:jma-2.0'
                   }
                }
            }
        }

        stage('deploy') {
            steps {
                script {
               
                }
             }
        }
    }
}