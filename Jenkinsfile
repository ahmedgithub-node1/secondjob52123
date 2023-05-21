@Library('my-shread-library') _

pipeline{

    agent any

    stages{

        stage('Git Checkout'){

            steps{

                script{

                    gitCheckout
                      branch: "main"
                      url: "https://github.com/ahmedgithub-node1/secondjob52123.git"
                    }
                }
            }
        }
    }   