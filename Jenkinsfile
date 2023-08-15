pipeline {
    agent any

    stages {
        stage ('Setup Environment') {
            steps {
                script {
                    //check if git istalled
                    def gitInstalled = sh(script: 'which git || true', returnStatus: true)
                    if (gitInstalled !=0) {
                        echo "Git is not installed. Installing now..."
                        sh 'sudo apt update && sudo apt install -y git'
                    } else {
                        echo "Git is already installed."
                         }
                    }
                }
            }
        
        stage ('Install Dependencies') {
            steps {
                script {
                    // check if unzip is installed
                    def hasUnzip = sh(script: 'which unzip || true', returnStatus: true)
                    if (hasUnzip != 0) {
                        echo "Installing unzip"
                        sh "sudo apt update"
                        sh "sudo apt install -y unzip"
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
                sudo unzip terraform.zip
                sudo mv terraform /usr/local/bin/
                terraform --version
                '''           //Unzip and Install
                }
            }
        }
    } 
}