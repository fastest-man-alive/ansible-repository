pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', changelog: false, credentialsId: 'github-sa', poll: false, url: 'https://github.com/fastest-man-alive/ansible-repository.git'
            }
        }

        stage('Run Ansible') {
            steps {
                ansiColor('xterm') {
                    sh 'ansible-playbook -i inventory.ini main.yml'
                }
            }
        }
    }
}