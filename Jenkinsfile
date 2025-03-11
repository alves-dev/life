pipeline {
    agent any
    stages {
        stage('Load Remote Jenkinsfile') {
            steps {
                script {
                    def remoteJenkinsfile = new URL('https://raw.githubusercontent.com/alves-dev/life/refs/heads/main/Jenkinsfile-old').text
                    evaluate(remoteJenkinsfile)
                }
            }
        }
    }
}
