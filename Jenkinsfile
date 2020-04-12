pipeline {
  agent any
  environment {
    INVENTORY = credentials('INVENTORY_INI')
    BRANCH = '{env.BRANCH_NAME}'
  }
  stages {
            stage('Checkout') {
                steps {
                    sh 'echo ${BRANCH}'
                    checkout scm
                }
             }
            stage('Create Inventory') {
                steps {
                    sh 'echo $INVENTORY  | base64 -d > inventory.ini'
                }
            }
            stage('Docker DM storage') {
                steps {
                    sh 'ansible-playbook -i inventory.ini docker-storage-setup-dm.yml'
            }
        }
    }
}