pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh ''' 
                echo "without docker"
                ls -al
                touch container-new.txt
                '''
            }
        }
        stage('w docker') {
            agent{
                docker {
                   image 'node:18-alpine'
                   reuseNode true
                }
            }
            steps {
                sh ''' 
                echo "with docker"
                npm --version
                ls -al
                touch container-new.txt
                
                '''
                
            }
        }
    }
}
