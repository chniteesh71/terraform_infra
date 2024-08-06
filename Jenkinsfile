#!/usr/bin/env groovy
pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = "us-east-1"
    }
    stages {
        stage("creating a iam user") {
            steps {
                script {
                    dir('terraform') {
                        sh "terraform init"
                        sh "terraform fmt"
                        sh "terraform validate"
                        sh "terraform plan"
                        sh "terraform apply -auto-approve"
                    }
                }
            }
        }
    }
}
