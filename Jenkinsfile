#!/usr/bin/env groovy
@Library('jenkins-sl')

def gv

pipeline {   
    agent any
    tools {
        maven 'maven-3.9'
    }
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                  buildJar()
                }
            }
        }

        stage("build and push image") {
            steps {
                script {
                  buildImage 'caster0515/demo-app:jma-3.0'
                  dockerLogin()
                  dockerPush'caster0515/demo-app:jma-3.0'
                }
            }
        }

        stage("deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }               
    }
} 