def remote = [:]
remote.name = "node-1"
remote.host = "3.128.198.19"
remote.allowAnyHosts = true

node {
    withCredentials([sshUserPrivateKey(credentialsId: '3.128.198.19', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.identityFile = identity
        stage("SSHing to Airflow Server") {
            sshCommand remote: remote, command: "echo \"SSH into Airflow Server Successful\""           
        }
        stage("Pulling Changes"){
            sshCommand remote: remote, command: "git -C /home/ubuntu/jenkins-poc/ pull"
        }
        stage("Executing Ariflow Commands"){
            sshCommand remote: remote, command: "python3 /home/ubuntu/jenkins-poc/Airflow-Folder/helloworld.py"
        }
    }
}