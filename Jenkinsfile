pipeline {
    agent any
    stages {
        stage ('vcs') {
          steps {
             git url:'https://github.com/nagendra4aa5/ec2ansible.git',
                 branch:'main' 
            }
        }
        stage ("terraform init") {
            steps {
                sh 'terraform init'
                sh 'terraform fmt'
                sh 'terraform validate'
                sh 'terraform apply "-lock=false" --auto-approve'
            }
        }
    }
}