pipeline {
    agent any 
    stages {
        stage('sshing') { 
            steps {
                sshagent (credentials: ['3.128.198.19']) {
                    sh 'cd /home/ubuntu'
                    sh 'touch trying.txt'
                    sh 'touch new_test.txt'
                }
            }
        }
    }
}