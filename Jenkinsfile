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
          echo 'Hello Sweden'
          sh "uname -m"
        }

//	def slackResponse = slackSend color: "good", message: "Fucking failure"
//	slackResponse.addReaction("thumbsup")
	def slackResponse = slackSend(channel: "emoji-demo", message: "Here is the primary message")
	slackResponse.addReaction("thumbsup")
    }
}
