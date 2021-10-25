pipeline {
    agent any 
    stages {
        stage('sshing') { 
            steps {
                sshagent (credentials: ['3.128.198.19']) {
                    ssh 'Hostname -I'
                }
            }
        }
    }
}