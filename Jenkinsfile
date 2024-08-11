pipeline{
    agent any
    stages{
        stage('checkout code from github'){
            steps{
                 git url: 'https://github.com/ssr2817/Banking-java-project.git'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with suraj'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with suraj'){
            steps{
                sh 'mvn test'
            }
        }
        stage('testing stage'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package the code'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
