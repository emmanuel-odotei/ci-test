pipeline {
    agent any

    environment {
        payroll_backend_staging_url = credentials('payroll_backend_staging_url')
    }
stages {
    stage('Smoke Test') {
                steps {
                        sh 'apt-get update'
                        sh 'apt-get install jq -y'
                        sh 'chmod +x ./scripts/smoke.sh'
                        sh './scripts/smoke.sh'
                }
                post {
                        failure {
                             script {
                                        echo "Smoke test failed. Simulating armsPostFailure"
                                   }
                             }
               }
    }
}

//     stages {
//         stage('Install dependencies') {
//             steps {
//                 sh 'apt-get update && apt-get install -y jq curl'
//             }
//         }
//
//         stage('Smoke Test') {
//             steps {
//                 sh 'chmod +x ./scripts/smoke.sh'
//                 sh './scripts/smoke.sh "$payroll_backend_staging_url"'
//             }
//             post {
//                 failure {
//                     script {
//                         echo "Smoke test failed. Simulating armsPostFailure"
//                     }
//                 }
//             }
//         }
//     }
}
