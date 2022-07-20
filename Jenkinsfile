pipeline {
    agent any


    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Cloning our Git') { 
            steps { 
                git 'https://github.com/foliemma/jenkistest.git' 
            }
        } 

        stage('Build') {
            steps {
                sh "mvn clean package" 
            }
        }
        // stage('Test') {
        //     steps {
        //         sh 'mvn clean test'
        //     }
        // }
        /*stage('Build Docker image') {
            steps {
                docker.build('cervello')
            }
        }
        stage('Push Docker image') {
            environment {
                DOCKER_HUB_LOGIN = credentials('dockerhub-cred-raja')
            }
            steps {
                sh 'docker login --username=$DOCKER_HUB_LOGIN_USR --password=$DOCKER_HUB_LOGIN_PSW'
                sh 'docker push cervello:latest'
                
            }
        }*/
       /*  stage('Deploy to AWS') {
            environment {
                DOCKER_HUB_LOGIN = credentials('dockerhub-cred-raja')
            }
            steps {
                withAWS(credentials: 'aws-credentials', region: env.AWS_REGION) {
                    sh './gradlew awsCfnMigrateStack awsCfnWaitStackComplete -PsubnetId=$SUBNET_ID -PdockerHubUsername=$DOCKER_HUB_LOGIN_USR -Pregion=$AWS_REGION'
                }
            }
        } */
    }
}
