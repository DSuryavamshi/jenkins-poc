def remote = [:]
remote.name = "node-1"
remote.host = "3.128.198.19"
remote.allowAnyHosts = true

node ('master'){
    withCredentials([sshUserPrivateKey(credentialsId: '3.128.198.19', keyFileVariable: 'identity', passphraseVariable: '', usernameVariable: 'userName')]) {
        remote.user = userName
        remote.identityFile = identity
        stage("Pulling Changes"){
            sshCommand remote: remote, command: """#!/bin/bash
            cd /home/ubuntu/jenkins-poc/
            git pull"""
        }
        stage("Executing Ariflow Commands"){
            sshCommand remote: remote, command: """#!/bin/bash
            cd /home/ubuntu/jenkins-poc/
            python3 Airflow-Folder/helloworld-test.py"""
            sshCommand remote: remote, command: "echo \"Process Complete.\""
        }
    }
}