pipeline {
    agent {
        label 'ansible'
    }
    stages {
        stage('Run Molecule Test'){
            steps {
                dir('hw-ansible-02/playbook/roles/vector') {
                    sh 'echo "We are in hw-ansible-02/playbook/roles/vector"'
                    sh 'ls -la'
                    sh 'molecule test'
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline Ended'
        }
    }
}