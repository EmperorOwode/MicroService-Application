pipeline {
    agent any
   // environment {
       // SCANNER_HOME = tool 'sonar-scanner'

 //  }

    stages {
         //   stage('SonarQube') {
       //      steps {
        //        withSonarQubeEnv('sonar-scanner') {
          //          sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.projectKey=Microservice_Deployment -Dsonar.ProjectName=Microservice_Deployment -Dsonar.java.binaries=.'''
            //    }
         //   }
       // }
            stage('adservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir('/var/lib/jenkins/workspace/Microservice_Deployment/src/adservice/') {
                        sh "docker build -t emperorowode/adservice:latest ."
                        sh "docker push emperorowode/adservice:latest"
                        sh "docker rmi emperorowode/adservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
            }
            stage('cartservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/cartservice/src/") {
                        sh "docker build -t emperorowode/cartservice:latest ."
                        sh "docker push emperorowode/cartservice:latest"
                        sh "docker rmi emperorowode/cartservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
       }
            stage('checkoutservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/checkoutservice/") {
                        sh "docker build -t emperorowode/checkoutservice:latest ."
                        sh "docker push emperorowode/checkoutservice:latest"
                        sh "docker rmi emperorowode/checkoutservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
            }
            stage('currencyservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/currencyservice/") {
                        sh "docker build -t emperorowode/currencyservice:latest ."
                        sh "docker push emperorowode/currencyservice:latest"
                        sh "docker rmi emperorowode/currencyservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }

            }
            stage('emailservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/emailservice/") {
                        sh "docker build -t emperorowode/emailservice:latest ."
                        sh "docker push emperorowode/emailservice:latest"
                        sh "docker rmi emperorowode/emailservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
            }
            stage('frontend') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/frontend/") {
                        sh "docker build -t emperorowode/frontend:latest ."
                        sh "docker push emperorowode/frontend:latest"
                        sh "docker rmi emperorowode/frontend:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
            }
            stage('loadgenerator') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/loadgenerator/") {
                        sh "docker build -t emperorowode/loadgenerator:latest ."
                        sh "docker push emperorowode/loadgenerator:latest"
                        sh "docker rmi emperorowode/loadgenerator:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
            }
             stage('paymentservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/paymentservice/") {
                        sh "docker build -t emperorowode/paymentservice:latest ."
                        sh "docker push emperorowode/paymentservice:latest"
                        sh "docker rmi emperorowode/paymentservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
             }
             stage('productcatalogservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/productcatalogservice/") {
                        sh "docker build -t emperorowode/productcatalogservice:latest ."
                        sh "docker push emperorowode/productcatalogservice:latest"
                        sh "docker rmi emperorowode/productcatalogservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
             }
             stage('recommendationservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/recommendationservice/") {
                        sh "docker build -t emperorowode/recommendationservice:latest ."
                        sh "docker push emperorowode/recommendationservice:latest"
                        sh "docker rmi emperorowode/recommendationservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
             }
             stage('shippingservice') {
              steps {
               script {
                 withDockerRegistry(credentialsId: 'dockerpass', toolName: 'docker') {
                    dir("/var/lib/jenkins/workspace/Microservice_Deployment/src/shippingservice/") {
                        sh "docker build -t emperorowode/shippingservice:latest ."
                        sh "docker push emperorowode/shippingservice:latest"
                        sh "docker rmi emperorowode/shippingservice:latest"
                        sh 'docker system prune -a -f --volumes'
                    }
                }
            }
        }
    }

              stage('EKS-Deployment') {
            steps {
                withKubeConfig(caCertificate: '', clusterName: 'dev_myAppp-eks-cluster', contextName: '', credentialsId: 'k8s', namespace: 'webapps', restrictKubeConfigAccess: false, serverUrl: 'https://164E26B4CF9979625E425CA707EABA03.gr7.us-east-1.eks.amazonaws.com') {
                    sh 'kubectl apply -f deployment-service.yaml'
                    sh 'kubectl get pods'
                    sh 'kubectl get svc'

                }
                }
            }
        }
   }
