pipeline {
    agent { label 'docker-agent' }
    scmVars = checkout scm
    stages {
        stage('build') {
            steps {
                sh 'docker --version'                
            }
        }
        stage('Init') {
            steps {
                echo 'Initializing..'
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL} and ${scmVars.GIT_BRANCH}"
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
