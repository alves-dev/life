pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh 'ls -la'
            }
        }
//         stage('Build 2') {
//             agent {
//                 docker {
//                     image 'gradle:8.2.0-jdk17-alpine'
//                     reuseNode true
//                 }
//             }
//             steps {
//                 sh 'gradle --version'
//             }
//         }
        stage('SSH') {
            steps {
                script {
                    def remote = [
                        name: 'Server 01',
                        host: '192.168.12.100',  // Use IP ou nome do host resolvível
                        allowAnyHosts: true
                    ]

                    withCredentials(
                        [
                            sshUserPrivateKey(
                                credentialsId: 'server01-ssh',
                                keyFileVariable: 'identity',
                                passphraseVariable: '',
                                usernameVariable: 'userName'
                            )
                        ]
                    ) {
                        remote.user = userName
                        remote.identityFile = identity

                        sshCommand remote: remote, command: 'echo "Executando no host via SSH"; ls -la /home'
                    }
                }
            }
        }

    }
}