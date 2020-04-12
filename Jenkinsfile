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
                    sh 'ansible-playbook -i inventory.ini docker-storage-setup-ofs.yml'
                }
            }
            stage('Docker DM storage') {
                steps {
                    sh 'ansible-playbook -i inventory.ini docker-storage-setup-ofs.yml'
            }
        }
    }
}