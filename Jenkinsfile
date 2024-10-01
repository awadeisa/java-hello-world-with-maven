pipeline{
    agent any

    tools {
         maven 'M3'
         jdk 'java'
    }

    stages{
        stage('checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/sreenivas449/java-hello-world-with-maven.git']]])
            }
        }
        stage('build'){
            steps{
             
                bat 'mvn -Dmaven.test.failure.ignore=true clean install'
            }
        }
    }
}
