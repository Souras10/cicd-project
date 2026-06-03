pipeline {
    agent any

    stages {
      stage('clone') {
         steps {
             git branch: 'main' , url: 'https://github.com/Souras10/cicd-project.git'
               }
            }

      stage('Build') {
         steps {
            sh 'docker build -t myapp .'
               }
           }
      
      stage('Run') {
         steps { 
            sh 'docker stop myapp-container || true'
            sh 'docker rm myapp-container || true'
            sh 'docker run -d -p 5000:5000 --name myapp-container myapp'
                }
            }
       }
    }
