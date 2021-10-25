// pipeline {
//     agent any 
//     stages {
//         stage('sshing') { 
//             // steps {
//             //     sshagent (credentials: ['3.128.198.19']) {
//             //         sh 'ssh ubuntu@3.128.198.19 \' Hostname -I\''
//             //     }
//             // }
        
//         }
//     }
// }
def remote = [:]
remote.name = "node-1"
remote.host = "3.128.198.19"
remote.allowAnyHosts = true

node {
    withCredentials([sshUserPrivateKey(credentialsId: '3.128.198.19', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.identityFile = identity
        stage("SSH Steps Rocks!") {
            sshCommand remote: remote, command: 'pwd'
            
        }
    }
}