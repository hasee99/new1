
pipeline {
    agent any
    stages {
        stage('check out') {
            steps {
              checkout scm
            }
        }
         stage('Build Image') {
            steps {
              sh 'docker build -t ubuntu_jenkins .'
            }
        }
         stage('Tag Image') {
           
            steps {
               sh 'docker tag ubuntu_jenkins:latest hasee658/ubuntu_jenkins:latest'
            }
        }
         stage('Push Image') {
          
            steps {
               sh 'docker login -u hasee658 -p Nasha@786#'
                sh 'docker push hasee658/ubuntu_jenkins:latest'
            }
        }
    }
    post { 
        aborted { 
            echo 'ABORTED'
        }
         success { 
            echo 'SUCCESS'
        }
         failure { 
            echo 'FAILURE'
        }
        changed { 
            echo 'FAILURE'
        }
    }
    
}
