pipeline {
    agent any

    stages {
        stage('Check-In') {
            steps {
                git branch: 'main', url: 'https://github.com/AshantaP/docker-build.git/'
            }
        }
        stage('Terraform-Plan') {
            steps {
                sh "terraform plan"
            }
        }
        stage('Terraform-Apply') {
            steps {
                sh "terraform apply -auto-approve"
            }
        }
        stage('Terraform-Destroy') {
            steps {
                input 'Do you want to destory'
                echo "Yes"
            }
        }
    }
}
