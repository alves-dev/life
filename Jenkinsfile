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
                sshCommand remote: [
                    name: 'meu-servidor',
                    host: 'sever01.alves-dev.com',
                    user: 'alves-dev',
                    credentialsId: 'meu-servidor-ssh'
                ], command: 'echo "Executando no host via SSH"; ls -la /home'
            }
        }

    }
}