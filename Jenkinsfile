@Library('shared-lib') _

pipeline{  

    agent any

    stages{

        stage('Git Checkout'){

            steps{
            gitCheckout(
                branch: "main"
                url: "https://github.com/ahmedgithub-node1/shared-lib.git"
            }
            }
        }
    }
}