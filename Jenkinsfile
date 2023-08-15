pipeline {
    agent any

    stages {
        stage ('Install Dependencies') {
            steps {
                script {
                    // check if unzip is installed
                    def hasUnzip = sh(script: 'which unzip || true', returnStatus: true)
                    if (hasUnzip ! = 0) {
                        echo "Unzip is not installed. Installing..."
                        sh '''
                            sudo apt-get update
                            sudo apt-get install -y unzip
                        '''
                    } else {
                        echo "Unzip is already installed."
                        }
                    }
                }
            }
        
        stage('Install Terraform') {
            steps {
                script {
                def terraformVersion = '1.5.4' //Updated to desired version
                def downloadUrl = "https://releases.hashicorp.com/terraform/${terraformVersion}/terraform_${terraformVersion}_linux_amd64.zip"
                sh "curl -o terraform.zip '${downloadUrl}'" // Download Terraform
                sh '''                               
                unzip terraform.zip
                sudo mv terraform /usr/local/bin/
                terraform --version
                '''           //Unzip and Install
                }
            }
        }
    } 
}