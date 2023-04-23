pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/dev']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'ae4f6f2b-bd6a-4930-8a82-de11b050d9a3', url: 'https://github.com/hita03/ecommerce-microservices-CC']]])
            }
        }

        stage('Build and Test') {
            steps {
                dir('product-service') {
                    bat 'start mvn clean package'
                }
                dir('inventory-service') {
                    bat 'start mvn clean package'
                }
                dir('order-service') {
                    bat 'start mvn clean package'
                }
                dir('notification-service') {
                    bat 'start mvn clean package'
                }
            }
        }

        stage('Build Docker Images') {
            steps {
                dir('product-service') {
                    script {
                        docker.withRegistry('https://registry.hub.docker.com','docker-registry-credentials')
                        {
                            bat 'docker push hitajuneja/product-service:latest'          	
                        }
                        docker.withRegistry('https://registry.hub.docker.com','docker-registry-credentials')
                        {
                            bat 'docker push hitajuneja/notification-service:latest'          	
                        }
                        docker.withRegistry('https://registry.hub.docker.com','docker-registry-credentials')
                        {
                            bat 'docker push hitajuneja/order-service:latest'          	
                        }
                        docker.withRegistry('https://registry.hub.docker.com','docker-registry-credentials')
                        {
                            bat 'docker push hitajuneja/inventory-service:latest'          	
                        }

                    }
                }
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                script{
                    bat 'kubectl apply -f k8s/services/product-service/'
                    bat 'kubectl apply -f k8s/services/order-service/'
                    bat 'kubectl apply -f k8s/services/inventory-service/'
                    bat 'kubectl apply -f k8s/services/notification-service/'
                }
            }
        }
    }
}
