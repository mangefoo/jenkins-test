podTemplate(
  label: 'jenkins-slave-2',
  containers: [
    containerTemplate(
      name: 'jnlp',
      image: 'synology:6000/inbound-agent:latest'
    )
  ]
) {
    node('jenkins-slave-2') {

        def myRepo = checkout scm

        stage('Hello') {
          echo 'Hello, world'
          sh "uname -m"
	  java -version
        }

//	slackSend color: "good", message: "Good"
//	slackSend color: "warning", message: "Warning"
//	slackSend color: "danger", message: "Danger"

//	def slackResponse = slackSend(channel: "jenkins-notifications", message: "Here is the primary message")
//	slackResponse.addReaction("thumbsup")

	def userId = slackUserIdFromEmail('magnus@mindphaser.se')
	slackSend(channel: userId, color: "good", message: "Automatic message from Jenkins Pipeline")
    }
}
