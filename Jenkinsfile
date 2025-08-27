pipeline{
    agent any
    environment{
        PATH = "/usr/local/bin:$PATH"
        AWS_ACCESS_KEY_ID = credentials('aws-access-key-id')
        AWS_SECRET_ACCESS_KEY = credentials('aws-secret-access-key')
    }
    stages{
        stage('checkout git repo'){
            steps{
                git branch: 'main',url: 'https://github.com/Yuga-23/terraform-demo.git',credentialsId:'github-credentials'

            }
        }
        stage('terraform init'){
            steps{
                sh 'terraform init'
            }
        }
        stage('terraform plan'){
            steps{
                sh 'terraform plan'
            }
        }
        stage('terraform apply'){
            steps{
                sh 'terraform apply -auto-approve'
            }
        }

    }
}