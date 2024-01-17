pipeline {
    agent any

    tools{
        jdk 'jdk17'
        nodejs 'node16'
    }
    environment {        
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')        
    }
    
    stages{        

        stage("Git Checkout") {            
            steps {
                script {
                    gitCheckout(
                        branch: "main",
                        url: "https://github.com/GopiChandAkkala/Deploy-TO-DO-App-using-ArgoCD.git"
                    )
                }
            }
        }
        
        stage('Npm'){          
            steps{
                sh 'npm install'
            }
        }
        
        stage("Docker Build Image") {            
            steps {
                script {
                    sh 'docker build -t akkalagopi/todo-app:latest .'
                }
            }
        }
       
        stage("Docker Image Push") {            
            steps {
                script {
                    sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                    sh "docker push akkalagopi/todo-app:latest"                         
                }
            }
        }
        
    }
    
}
