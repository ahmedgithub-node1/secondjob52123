@Library('shared-lib') _

pipeline{  

    agent any

    stages{

        stage('Git Checkout'){

            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/ahmedgithub-node1/secondjob52123.git"
            )
            }
        }
         stage('Unit Test maven'){

            steps{
                script{

                    mvnTest()
                }
            }
        }
         stage('Integration Test maven'){

            steps{
                script{

                    mvnintegrationtesting()
                }
            
            }
        }
    }
}