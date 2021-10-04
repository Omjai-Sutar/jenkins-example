 

// pipeline{
//     agent any

//     stages{
//      stage("Hello Demo"){
//         steps{
//             echo"Hello world"
//         }
//     }
//         stage("Email notification"){
//             steps{
//              emailext(to:'omjaisutar1010@gmail.com',replyTo:'omjaisutar1010@gmail.com', subject:"Email Report from-'${env.JOB_NAME}'",
//                      ,body:"It Works",
//                      mimeType:'text/html');
             
//                }
//         }
//     }
// }



// pipeline{
//     agent any

//     stages{
//      stage("Hello Demo"){
//         steps{
//             echo"Hello world"
//         }
//     }
//         stage("Email notification"){
//             steps{
// //              emailext(to:'tejasi.chavan07@gmail.com',replyTo:'omjaisutar1010@gmail.com', subject:"Email Report from-'${env.JOB_NAME}'",
// //                       ,body:"${currentBuild.result}:${BUILD_URL}",
// //                      mimeType:'text/html');
//              emailext attachLog: true, 
//              body: "${currentBuild.result}: ${BUILD_URL}", 
//              compressLog: true, replyTo: 'omjaisutar1010@gmail.com',
//              subject: "Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}", 
//              to: 'omjaisutar1010@gmail.com'
             
//                }
//         }
//      stage("Slack notification")
//      {
//       steps{
      
//        slackSend baseUrl: 'https://hooks.slack.com/services/',
//         channel: '#slack-notification-jenkins',
//         color: 'good',
//         message: 'Welcome to slack notification', 
//         teamDomain: 'jenkinpipelinedemo', 
//         tokenCredentialId: 'slack-demo'
      
//       }
//      }
//     }
// }














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
             emailext attachLog: true, 
             body: "${currentBuild.result}: ${BUILD_URL}", 
             compressLog: true, replyTo: 'omjaisutar1010@gmail.com',
             subject: "Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}", 
             to: 'omjaisutar1010@gmail.com'
             
               }
        }
     stage("Slack notification")
     {
      steps{
      
       myVariable = "foo"
       
       slackSend baseUrl: 'https://hooks.slack.com/services/',
        channel: '#slack-notification-jenkins',
        color: 'good',
        message: 'Welcome to slack notification', 
        teamDomain: 'jenkinpipelinedemo', 
        tokenCredentialId: 'slack-demo'
       
       echo "My variable is ${myVariable}"
      }
     }
    }
}


