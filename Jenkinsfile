// To mark start of our Pipeline
pipeline{ 

    // On which Jenkins agent do we want to execute the Pipeline
    agent any

    // Add Env Vars
    environment{
        VERSION_NAME = "1.34"
    }

    // Stages which we will be having in the Pipeline
    stages{
        stage("compile"){
            steps{
                sh 'javac Test.java'
                sh 'echo "${VERSION_NAME}"'
            }
        }

        stage("run"){
            steps{
                sh "java Test"
            }
        }

        // stage("build"){
        //     // Steps in the Stage
            // steps{
        //         // Here we write scripts like Shell
        //         // By sh means we are on Terminal
        //         sh 'echo "Building Application"'
        //     }
        // }

        // stage("test"){
        //     steps{
        //         sh 'echo "Testing Application"'
        //     }
        // }

        // stage("deploy"){
        //     steps{
        //         sh 'echo "Deploying Application"'
        //     }
        // }
    }

    // Post Build : 
    post{

        // Always
        always{
            sh 'echo "Always Run - Fail or Success"'
        }

        // If Success
        success{
            sh 'echo "Build Success"'
        }

        failure{
            sh 'echo "Build Failed"'
        }
    }


}