pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Assuming you have your Ansible playbook in a SCM like Git
                checkout scm
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Ensure Ansible is in the PATH
                    sh 'export PATH=$PATH:/path/to/ansible'

                    // Run the playbook
                    sh 'ansible-playbook install_httpd.yaml'
                }
            }
        }
    }

    post {
        success {
            echo 'Playbook executed successfully!'
        }
        failure {
            echo 'Playbook execution failed!'
        }
    }
}