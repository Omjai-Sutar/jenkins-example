 

pipeline{
    agent any

    stages{
     stage("Hello Demo"){
        steps{
            echo"Hello world"
        }
    }
        stage("Email notification"){
            steps{
             emailext(to:'omjaisutar1010@gmail.com',replyTo:'omjaisutar1010@gmail.com', subject:"Email Report from-'${env.JOB_NAME}'",
                     ,body:readFile("target/surefire-reports/emaillable-report.html"),
                     mimeType:'text/html');
              //email body: 'Success!', subject: 'Pipeline status ', to: 'omjaisutar1010@gmail.com'
               // emailext attachLog: true,body: 'Build JOB has failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'],[$class: 'RequesterRecipientProvider']], to: "omjaisutar1010@gmail.com", subject: "Job '${env.JOB_NAME}'- (${version}) has failed"
            }
        }
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
