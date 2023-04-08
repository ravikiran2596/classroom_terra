pipeline {
    agent any
    stages {
        stage (vcs) {
            steps {
                git url: 'https://github.com/ravikiran2596/classroom_terra.git'
                    branch: 'master'
            }
            stage (init) {
                sh 'terraform init'
            }
            stage (fmt) {
                sh 'terraform fmt'
            }
            stage (validate) {
                sh 'terraform validate'
            }
            stage (apply) {
                sh 'terraform apply -var-file variables.tfvars'
            }
        }
    }
}