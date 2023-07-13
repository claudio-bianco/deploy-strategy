pipeline {
    agent { label 'docker-agent' }
    stages {
        stage('build') {
            steps {
                sh 'docker --version'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub', url: 'https://github.com/claudio-bianco/deploy-strategy.git']])
            }
        }
    }
}
