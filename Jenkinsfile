pipeline {
    agent { label 'Docker' }
    triggers { 
        pollSCM('* * * * *')
    }
    stages {
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
