pipeline {
    agent any

    stages {
      
        stage('TFLint') {
            steps {
                    sh 'tflint --init'
                    sh 'tflint'
                
            }
        }

        stage('TFSec') {
            steps {
                sh 'tfsec'
            }
        }

        // stage('Terratest') {
        //     steps {
        //            dir('test') {
        //             sh 'if [ ! -f go.mod ]; then go mod init github.com/galesme/ci-cd-pipeline-jenkins-lab; fi'
        //             sh 'go mod tidy'
        //             sh 'go test'
        //            }
        //         }
        //     }
        

        stage('Terraform workflow') {
            steps {
                    sh 'terraform init'
                    sh 'terraform plan -out=tfplan'
                    sh 'terraform apply -auto-approve tfplan'
            }
        }   
    }
}
