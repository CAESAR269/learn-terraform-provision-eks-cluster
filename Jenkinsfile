pipeline {
    agent { label 'Docker' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: 'https://github.com/CAESAR269/learn-terraform-provision-eks-cluster.git',
                    branch: 'main'
            }
        }
        stage('terraform') {
            steps {
                sh 'terraform init'
                sh 'terraform validate'
                sh 'terraform plan'
                sh 'terraform apply --auto-approve'
            }
        }
    }
}
