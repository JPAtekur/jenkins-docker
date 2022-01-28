pipeline{
    agent any
    tools{
        maven 'apache-maven-3.6.0'
    }
    stages{
        stage('build'){
             steps {
                echo 'Building application'
            }
        }
        stage('test'){
            steps{
                echo 'Testing application'
            }
        }
        stage('deploy'){
            steps{
                echo 'Deploying application'
                sh 'mvn --version'
            }
        }
    }
}