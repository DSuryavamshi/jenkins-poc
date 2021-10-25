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
            // writeFile file: 'abc.sh', text: 'ls'
            sshCommand remote: remote, command: 'pwd'
        //     sshPut remote: remote, from: 'abc.sh', into: '.'
        //     sshGet remote: remote, from: 'abc.sh', into: 'bac.sh', override: true
        //     sshScript remote: remote, script: 'abc.sh'
        //     sshRemove remote: remote, path: 'abc.sh'
        }
    }
}