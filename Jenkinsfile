pipeline {
    agent any

    stages {
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
        stage('Build') {
            agent {
                docker {
                    image 'gradle:8.2.0-jdk17-alpine'
                    reuseNode true
                }
            }
            steps {
                sh 'gradle --version'
            }
        }
        stage('SSH') {
            steps {
                script {
                    def remote = [
                        name: 'Server 01',
                        host: env.SERVER_01_IP,
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