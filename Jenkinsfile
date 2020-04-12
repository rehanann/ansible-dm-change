pipeline {
  agent any
  stages {
            stage('Checkout') {
                steps {
                    checkout scm
                }
             }
            stage('Create Inventory') {
                steps {
                    sh 'base64 -d ${INVENTORY} > inventory.ini'
                }
            }
            stage('Docker DM storage') {
                steps {
                    sh 'ansible-playbook -i inventory.ini docker-storage-setup-ofs.yml'
            }
        }
    }
}