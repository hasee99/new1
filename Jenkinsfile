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
              bat 'docker build -t node00 -f Dockerfile  .'
            }
        }
         stage('Tag Image') {
            steps {
               bat 'docker tag node00 hasee658/node00'
            }
         }
        stage('Push Image') {
            steps {
               bat 'docker login -u hasee658 -p Nasha@786'
                bat 'docker push hasee658/node00'
            }
        }
        stage ('Run Image') {
            steps {
            bat 'docker run --name Conm -p 7778:3070 -d  node001'
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

