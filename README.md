# Terraform_installation
This repo will install Terraform with Jenkins pipeline
This will require manual interaction to server. Sudoers file need to be updated 
sudo visudo
then 
jenkins ALL=(ALL:ALL) NOPASSWD: /usr/bin/unzip
jenkins ALL=(ALL:ALL) NOPASSWD: /usr/bin/apt
jenkins ALL=(ALL) NOPASSWD: /usr/bin/mv * /usr/local/bin/

