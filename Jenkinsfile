pipeline{
    agent any
    
    environment {
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage('build'){
             steps {
                echo 'Building application'
                sh 'mvn --version'
                sh 'mvn install'
            }
        }
        stage('Dockerize application'){
            agent{
                docker{
                    image 'alpine'
                }
            }
            steps{
                script{
                    withCredentials([string(credentialsId: 'docker_pass', variable: 'docker_password')]) {
                        sh '''
                            docker build -t atekur/docker-jenkins:${VERSION} .
                            docker login -u atekur -p $docker_password
                            docker push atekur/docker-jenkins:${VERSION}
                        '''
                    }
                   
                }
            }
        }
        stage('deploy'){
            steps{
                echo 'Deploying application'
                
            }
        }
    }
}
