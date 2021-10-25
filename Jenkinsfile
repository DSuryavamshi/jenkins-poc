def remote = [:]
remote.name = "node-1"
remote.host = "3.128.198.19"
remote.allowAnyHosts = true

node {
    withCredentials([sshUserPrivateKey(credentialsId: '3.128.198.19', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.identityFile = identity
        stage("SSH Steps Rocks!") {
            sshCommand remote: remote, command: "cd /home/ubuntu/jenkins-poc/"
            sshCommand remote: remote, command: "pwd"
            sshCommand remote: remote, command: "git pull"
            sshCommand remote: remote, command: "python3 helloworld.py"
        }
    }
}