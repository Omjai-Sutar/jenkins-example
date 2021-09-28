
pipeline{
    agent any

    stages{
     stage("Hello Demo"){
        steps{
            echo"Hello world"
        }
    }
        stage("Email notification"){
            emailext body: 'Success!', subject: 'Pipeline status ', to: 'omjaisutar1010@gmail.com'
    }
}

// pipeline {
//     agent any
     
//     stages {
//         stage('Ok') {
//             steps {
//                 echo "Ok"
//             }
//         }
//     }
//     post {
//         always {
//             emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
//         }
//     }
// }
