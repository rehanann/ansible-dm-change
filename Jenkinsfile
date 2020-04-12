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
                    // sh 'echo ${INVENTORY_FILE} | base64 -d'
                    // sh 'base64 -d ${INVENTORY_FILE} > inventory.ini'
                    sh 'cp /var/lib/jenkins/mytest-secrets/inventory.ini inventory.ini'
                }
            }
            stage('Docker DM storage') {
                steps {
                    sh 'ansible-playbook -i inventory.ini docker-storage-setup-dm.yml'
            }
        }
    }
}