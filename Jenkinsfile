@Library('shared-lib') _

pipeline{  

    agent any

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
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
                scripts{

                    statiCodeAnalyses()
               }
            }   
        }
    }
}