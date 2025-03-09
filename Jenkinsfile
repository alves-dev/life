pipeline {
    agent any
    stages {
        stage('Load Remote Jenkinsfile') {
            steps {
                script {
                    def remoteJenkinsfile = new URL('https://github.com/alves-dev/life/blob/main/Jenkinsfile-old').text
                    evaluate(remoteJenkinsfile)
                }
            }
        }
    }
}
