@Library('shared-lib') _

pipeline{  

    agent any

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
        string(name: 'ImageName', description: "name of the docker build", defaultValue: 'javapp')
        string(name: 'ImageTag', description: "tag of the docker build", defaultValue: 'v1')
        string(name: 'AppName', description: "name of the docker Application", defaultValue: 'springboot')
    }

    stages{

        stage('Git Checkout'){
                    when { expression { params.action == 'create' } }
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/ahmedgithub-node1/secondjob52123.git"
            )
            }
        }
         stage('Unit Test maven'){

         when { expression { params.action == 'create' } }
            
            steps{
               script{

                    mvnTest()
               }
            }
        }
         stage('Integration Test maven'){
         when { expression { params.action == 'create' } }
            steps{
                script{

                    mvnintegrationtesting()
               }
            }     
        }
        stage('Static code analyses: Sonarqube'){
         when { expression { params.action == 'create' } }
            steps{
                script{

                    def SonarqubecredentialsId = 'sonar-apimi'
                    statiCodeAnalyses(SonarqubecredentialsId)
               }
            }   
        }
        stage('Quality Gate Status Check: Sonarqube'){
         when { expression { params.action == 'create' } }
            steps{
                script{

                    def SonarqubecredentialsId = 'sonar-apimi'
                    QualitygateStatus(SonarqubecredentialsId)
               }
            }   
        }
        stage('Maven Build : maven'){
         when { expression { params.action == 'create' } }
            steps{
                script{

                    mvnBuild()
               }
            }   
        }
        stage('Dockcer Image build'){
         when { expression { params.action == 'create' } }
            steps{
                script{

                    dockerBuild("${params.ImageName}","${params.ImageTag}","${params.AppName}")
               }
            }   
        }
    }
}