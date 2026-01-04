// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building the application...'
//             }
//         }

//         stage('Test') {
//             steps {
//                 echo 'Running tests...'
//             }
//         }

//         stage('Deploy') {
//             steps {
//                 echo 'Deploying application...'
//             }
//         }
//     }
// }
pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Compiling source code...'
                bat 'echo Build successful > build_report.txt'
            }
        }

        stage('Test') {
            steps {
                echo 'Executing unit tests...'
                bat 'echo All tests passed >> build_report.txt'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                bat 'echo Deployment completed >> build_report.txt'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully'
        }
        failure {
            echo 'Pipeline execution failed'
        }
        always {
            archiveArtifacts artifacts: 'build_report.txt'
        }
    }
}
