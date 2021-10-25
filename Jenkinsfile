pipeline {
    agent any 
    stages {
        stage('sshing') { 
            // steps {
            //     sshagent (credentials: ['3.128.198.19']) {
            //         sh 'ssh Hostname -I'
            //     }
            withCredentials([sshUserPrivateKey(credentialsId: 'sshUser', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
                sh 'echo ${userName}'
            }
        }
    }
}

// def remote = [:]
// remote.name = "node-1"
// remote.host = "10.000.000.153"
// remote.allowAnyHosts = true

// node {
//     withCredentials([sshUserPrivateKey(credentialsId: 'sshUser', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
//         remote.user = userName
//         remote.identityFile = identity
//         stage("SSH Steps Rocks!") {
//             writeFile file: 'abc.sh', text: 'ls'
//             sshCommand remote: remote, command: 'for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done'
//             sshPut remote: remote, from: 'abc.sh', into: '.'
//             sshGet remote: remote, from: 'abc.sh', into: 'bac.sh', override: true
//             sshScript remote: remote, script: 'abc.sh'
//             sshRemove remote: remote, path: 'abc.sh'
//         }
//     }
// }