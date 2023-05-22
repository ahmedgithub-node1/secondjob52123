@Library('shared-lib') _

pipeline{

    agent any

    stages{

        stage('Git Checkout'){

            steps{
            gitCheckout{
                branch: "master"
                url: "https://github.com/ahmedgithub-node1/secondjob52123.git"
            }    
            }
        }
    }
}