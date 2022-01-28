pipeline{
    agent any
    tools{
        maven 'maven'
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
