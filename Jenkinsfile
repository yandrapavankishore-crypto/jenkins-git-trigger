
pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Pull GitHub Code') {
            steps {
                dir('github-code') {
                    git branch: 'develop',
                        url: 'https://github.com/yandrapavankishore-crypto/jenkins-git-trigger.git'
                }
            }
        }

        stage('Verify Downloaded Files') {
            steps {
                sh '''
                    echo "GitHub code downloaded successfully"
                    pwd
                    ls -la github-code
                    cat github-code/index.html
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
