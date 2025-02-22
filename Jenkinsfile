pipeline {
    agent any
    
    stages {

        stage('test') {
            steps {
                script {
                   gv.buildJar()
                }
            }
        }

            stage('build') {
            when {
                expression {
                   BRANCH_NAME == "master" 
                }
            }    
            steps {
                script {
                  gv.buildImage()
                   }
                }
            }

            stage('deploy') {
            when {
             expression {
                   BRANCH_NAME == "master" 
                }
            steps {
                script {
                 gv.deployApp()
                }
             }
        }
    }
}

}