pipeline {
    agent any
    
    stages {
        stage ('vcs') {
            steps {
                git url: 'https://github.com/ravikiran2596/classroom_terra.git',
                    branch: 'master'
            }
            stage ('ok') {
                steps {
                    sh 'terraform init'
                }
            }
            stage ('done') {
                steps {
                    sh 'terraform fmt'
                }
            }
            stage ('check') {
                steps {
                    sh 'terraform validate'
                }
            }
            stage ('do') {
                steps {
                    sh 'terraform apply -var-file variables.tfvars'
                }
            }
        }
    }
}