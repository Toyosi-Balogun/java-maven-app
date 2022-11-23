#!/usr/bin/env groovy

library identifier: 'jenkins-shared-library@master', retriever: modernSCM(
        [$class: 'GitSCMSource',
         remote: 'https://gitlab.com/nanuchi/jenkins-shared-library.git',
         credentialsId: 'gitlab-credentials'
        ]
)


def gv

pipeline {
    agent any
    tools {
        maven 'Maven'
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
<<<<<<< HEAD
                    buildImage 'nanajanashia/demo-app:jma-3.0'
                    dockerLogin()
                    dockerPush 'nanajanashia/demo-app:jma-3.0'
=======
                    buildImage 'typhoenix/my-app:jma-3.0'
                    dockerPush 'typhoenix/my-app:jma-3.0'
>>>>>>> fb1d1c5032b1d7ce316494013943d4e04a100f7b
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
