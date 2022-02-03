pipeline{
    agent any
    environment {
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage('build'){
             steps {
                echo 'Building application'
                bat './mvnw install'
            }
        }
        stage('Dockerize and push'){
            
            steps{
                bat 'docker build -t atekur/docker_jenkins:%VERSION% .'
                bat 'docker push atekur/docker_jenkins:%VERSION%'
            }
        }
    }
}
