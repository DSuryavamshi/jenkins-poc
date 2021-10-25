pipeline {
    agent any 
    stages {
        stage('sshing') { 
            steps {
                sshagent (credentials: ['3.128.198.19']) {
                    sh 'ssh ubuntu@3.128.198.19 \' Hostname -I\''
                }
            }
        }
    }
}
