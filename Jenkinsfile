pipeline {

    stages {
        stage('Install Terraform') {
            steps {
                def terraformVersion = '1.5.4' //Updated to desired version
                def downloadUrl = "https://releases.hashicorp.com/terraform/${terraformVersion}/terraform_${terraformVersion}_linux_amd64.zip"

                // Download Terraform
                sh "curl -o terraform.zip '${downloadUrl}'"

                // Unzip and Install
                sh '''
                unzip terraform.zip
                sudo mv terraform /usr/local/bin/
                terraform --version
                '''
            }
        }
    }
} 
