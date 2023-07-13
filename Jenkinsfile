pipeline {
    agent { label 'docker-agent' }    
    stages {
        stage('build') {
            steps {
                sh 'docker --version'
                sh 'printenv'
            }
        }
        stage('Init') {
            steps {
                echo 'Initializing..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "Current branch: ${env.GIT_BRANCH}"
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
