#!/usr/bin/env groovy

node{
    stage("Git Checkout"){
        git 'https://github.com/2mpsanketh/DevOpsClassCodes.git'
    }
    stage("Compile"){
        withMaven(maven:"MyFirstMaven"){
            sh "mvn compile"
        }
    }
    stage("Test & publish Test results"){
        try{
            withMaven(maven:"MyFirstMaven"){
                sh "mvn test"
            }
        }finally{
            junit 'target/surefire-reports/*.xml'
        }
    }
    stage("Package"){
        withMaven(maven:"MyFirstMaven"){
            sh "mvn package"
        }
    }
}
