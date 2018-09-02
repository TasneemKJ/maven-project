pipeline {
    agent any

    stages{
        stage('Build'){
        agent {
                dockerfile {
                  filename 'Dockerfile'
                  label 'windocker'
                }
                }
            steps{
                bat 'mvn clean package'
                bat "docker build . -t tomcatwebapp:${env.BUILD_ID}"
            }

        }
    }
}