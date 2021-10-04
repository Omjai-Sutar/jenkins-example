 

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

 
//  try {
 
//     stages{
//      stage("Hello Demo"){
//         steps{
//             echo"Hello world"
//         }
//     }
//         stage("Email notification"){
//             steps{
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
  
       
//         slackSend baseUrl: 'https://hooks.slack.com/services/',
//         channel: '#slack-notification-jenkins',
//         color: 'good',
//         message: 'Welcome to slack notification', 
//         teamDomain: 'jenkinpipelinedemo', 
//         tokenCredentialId: 'slack-demo'
       
//      }
//      }
     
//     }
//   echo 'This will run only if successful'
//             currentBuild.result = 'SUCCESS'
//    } 
//  catch (e) {
//         echo 'This will run only if failed'

//         currentBuild.result = 'FAILURE'
 
//         throw e
//     } finally {

//     if ( "${currentBuild.result}" == 'FAILURE' ) {
//         echo 'JOB failed'
//         emailext attachLog: true,body: 'Build JOB has failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'],[$class: 'RequesterRecipientProvider']], to: "${env.gitlabUserEmail}", subject: "Job '${env.JOB_NAME}'- (${version}) has failed"
//         }

//         }
// }






def notifySlack(String buildStatus = 'STARTED') {
    // Build status of null means success.
    buildStatus = buildStatus ?: 'SUCCESS'

    def color

    if (buildStatus == 'STARTED') {
        color = '#D4DADF'
    } else if (buildStatus == 'SUCCESS') {
        color = '#BDFFC3'
    } else if (buildStatus == 'UNSTABLE') {
        color = '#FFFE89'
    } else {
        color = '#FF9FA1'
    }

    def msg = "${buildStatus}: `${env.JOB_NAME}` #${env.BUILD_NUMBER}:\n${env.BUILD_URL}"

    slackSend(color: color, message: msg)
}

node {
    try {
        notifySlack()

        // Existing build steps.
    } catch (e) {
        currentBuild.result = 'FAILURE'
        throw e
    } finally {
        notifySlack(currentBuild.result)
    }
}
