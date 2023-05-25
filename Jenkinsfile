@Library('shared-lib') _

pipeline{  

    agent any

    parameters{

        choice(name: 'action', choice: 'create\ndelete', description: 'choose create\destroy' )
    }

    stages{

        when { expresion { param.action == 'create'
        } }
        stage('Git Checkout'){

            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/ahmedgithub-node1/secondjob52123.git"
            )
            }
        }
         stage('Unit Test maven'){

            when { expresion { param.action == 'create'
            
            steps{
                script{

                    mvnTest()
                }
            }
        }
         stage('Integration Test maven'){
         when { expresion { param.action == 'create'
            steps{
                script{

                    mvnintegrationtesting()
                }
            
            }
         stage('Static code analyses: Sonarqube'){
         when { expresion { param.action == 'create'
            steps{
                script{

                    statiCodeAnalyses()
                }
            
            }
        }
    }
}