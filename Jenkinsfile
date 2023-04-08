pipeline {
    agent any
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/ravikiran2596/classroom_terra.git',
                    branch: 'master'
            }
        }
        stage('init') {
            steps {
                sh 'terraform init'
            }
        }
        stage('fmt') {
            steps {
                sh 'terraform fmt'
            }
        }
        stage('validate') {
            steps {
                sh 'terraform validate'
            }
        }
        stage('apply') {
            steps {
                sh 'terraform apply -auto-approve -var-file variables.tfvars'
            }
        }
    }
}