pipeline {
    agent { label 'docker-agent' }
    stages {
        stage('build') {
            steps {
                sh 'docker --version'
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'GitHub', url: 'https://github.com/claudio-bianco/deploy-strategy.git']])
            }
        }
        stage('Init') {
            steps {
                echo 'Initializing..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "Current branch: ${env.BRANCH_NAME}"
                echo "Current tag: ${env.TAG_NAME}"
            }
        }
        stage('AWS') {           
            steps {
                echo 'AWS command..'
                sh '''
                  aws --version
                  aws ec2 describe-instances
                '''
            }
        }        
    }
}
